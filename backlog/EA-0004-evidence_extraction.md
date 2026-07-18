# Feature Brief: EA-0004 — Evidence Extraction

**Slug**: evidence_extraction
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational (fourth domain feature; depends only on EA-0003)
**Status**: BRIEF-DRAFT

---

## Problem / Need

A research corpus is just collected material — nobody can yet point to which passage
supports which idea, or why it was worth collecting at all. Without this feature, every
downstream stage would have to independently rediscover relevant passages, interpret them,
and reconstruct why they matter to the investigation: evidence selection becomes
inconsistent across attempts, traceability back to source material becomes fragile, and
claim construction would have to start from raw documents instead of explicit, reviewable
evidence.

## Primary Actor

**Correction (2026-07-18, per Architecture Journal AJ-003):** the actor for this feature is
the **Knowledge Reviewer** — a single role that also covers what EA-0005 and EA-0006
separately called "Ambiguity Reviewer" and "Claim Reviewer." (This section previously named
a standalone "Evidence Reviewer"; that name is retired in favor of the unified role.) The
Knowledge Reviewer's question here specifically is whether a proposed candidate evidence
item is suitable to enter the project's evidence base — a different question from what the
same role asks when reviewing a claim or an ambiguity, but the same role, not a separate
actor. Today, without this feature, that evaluation can't happen at all — the reviewer
would have to search raw documents, choose passages, interpret them, and reconstruct
relevance themselves, which is exactly the duplicated, inconsistent work this feature
exists to remove.

## Core Outcome (informal)

The Knowledge Reviewer can efficiently determine whether a proposed candidate evidence item
is suitable to become part of the project's evidence base — without having to reconstruct
the research process or rediscover the supporting material themselves. The feature has
already done the expensive preparation (locating the passage, capturing it faithfully,
interpreting it, and explaining why it belongs to the investigation); the reviewer's job
becomes evaluation, not investigation. Concretely, that single "fit for acceptance"
decision rests on three distinguishable questions later Stage 1/2 work should keep
separate: was the right passage *selected* for this Research Question, does the
*interpretation* stay grounded in what the passage actually says, and does that
interpretation actually *advance* the Research Question it's linked to. This feature
doesn't decide any of the three — it produces evidence structured so the Knowledge
Reviewer, through EA-0008 (Knowledge Review), can decide efficiently.

## Design Tensions and Open Questions

1. **Should this be one feature, or split into passage-selection and interpretation?**
   [Resolved: one feature. The deciding test is the same one that justified splitting
   EA-0002 from EA-0003: does the earlier stopping point have independent actor value? A
   Research Plan does — an editor can review a strategy before spending resources. A pile
   of highlighted-but-uninterpreted passages doesn't — no reviewer benefits from evaluating
   spans of text with no sense of what they're claimed to support. A future split would be
   scalability-driven (very large corpora, separate retrieval models, passage reuse across
   many interpretations at scale), not a mechanical-vs-interpretive one — not applicable for
   v1.]
2. **Where's the line between this feature's self-verification and EA-0008's (Knowledge
   Review's) acceptance decision?** [Resolved as a principle: this feature may only verify
   narrow, structural/grounding properties — the source belongs to the approved corpus, the
   locator resolves to the cited passage, the excerpt is faithful and unaltered (truncation
   disclosed), sufficient context was captured, required fields are present, the
   interpretation doesn't visibly introduce facts absent from the source, and
   duplicate/overlapping records are flagged. It may never assert that a candidate is
   *accepted* — only that it's structurally complete and apparently grounded. The "visibly
   introduce unsupported facts" check sits closest to the line, since it requires some
   semantic comparison, not pure structure-checking — flagged for Stage 1/2 to tighten if
   needed. Everything about substantive acceptance (does the interpretation actually hold
   up, is it too broad, are qualifications missing, accept/reject/return-for-revision)
   belongs to EA-0008 (Knowledge Review), owned by the Knowledge Reviewer. These are
   recorded here as **assumptions requiring validation by that brief**, not decisions this
   feature owns — this feature produces Candidate Evidence; only EA-0008 produces Accepted
   Evidence.]
3. **What happens when no passage can be found for a Research Question?** [Resolved:
   report it explicitly as an investigation finding, not a retrieval failure — e.g. "no
   candidate evidence identified in the approved corpus for RQ-3." This says nothing about
   reality, only about what this corpus contains, and is itself valuable information rather
   than an error to hide.]
4. **What happens when one passage is relevant to multiple Research Questions?**
   [Resolved: extract once, link to many — a single candidate evidence item can reference
   several Research Questions rather than being duplicated per question. Duplicating it
   would create multiple copies of the same evidence that could drift independently, the
   same "multiple mutable sources of truth" risk already flagged architecturally in
   `docs/solution-discovery-evidenceatlas.md`.]
5. **How should corroboration between independent sources be distinguished from mechanical
   duplication?** [Resolved as a principle: this feature may recognize mechanical
   duplication (e.g. a wire-service article republished verbatim) but must not collapse
   independent agreement between genuinely distinct sources into "duplicate" — that
   agreement is valuable signal for later stages, not redundancy. This feature doesn't
   reason about *what* corroboration means or aggregate it; it only avoids destroying the
   distinction. **Open nuance:** telling "mechanically identical/republished" apart from
   "independently produced but agreeing" is itself a judgment call that isn't fully
   specified here — left for Stage 2 to define concretely.]
6. **Does this feature do any new source discovery?** [Resolved: no, hard boundary. It
   operates only over the already-approved Research Corpus from EA-0003 — no web search,
   no new crawling, no "just one more source." Crossing this boundary would make the
   provenance chain impossible to reconstruct.]
7. **Naming:** the feature name "Evidence Extraction" stays workable (it matches the
   discovery doc's existing vocabulary — Evidence is already defined as excerpt +
   interpretation), but its *output* should use provisional language (e.g. "Candidate
   Evidence") rather than implying accepted evidence emerges automatically.

## Suspected Dependencies

Upstream: EA-0003 (Research Corpus + Research Execution Report) only.

Downstream (hard): EA-0008 (Knowledge Review) consumes Candidate Evidence directly, and its
Knowledge Reviewer evaluates it. The accept/reject/return-for-revision behavior, and the
expectation that any revised interpretation produces a traceable new version rather than a
silent rewrite, are owned by EA-0008, not this feature.

**Correction (2026-07-17, during EA-0006 Round 0; actor/feature names updated 2026-07-18
per AJ-003):** Claim Construction (EA-0006) does **not** consume Candidate Evidence
directly, despite what an earlier version of this section said. It consumes **Accepted
Evidence**, the artifact state produced once EA-0008 (Knowledge Review) accepts a
candidate — otherwise unreviewed, possibly-hallucinated candidates could influence claim
synthesis before the human acceptance step meant to catch that. The chain is: this feature
produces Candidate Evidence → EA-0008 (Knowledge Review) produces Accepted Evidence →
EA-0006 (Claim Construction) consumes Accepted Evidence. EA-0006's dependency on this
feature's output is indirect, mediated through EA-0008's acceptance decision, not a direct
dependency on Candidate Evidence itself.

Downstream (soft): EA-0005 (Ambiguity Construction) is the deliberate exception to the
correction above — its pre-claim path explicitly accepts manually-referred Candidate
Evidence pairs directly from this feature, without requiring EA-0008's acceptance first,
since that path is explicitly analytical/provisional (it can conclude "no real conflict" or
"insufficient context") and doesn't promote those candidates into the accepted evidence
base. Not a hard dependency in the sense of being required for this feature to run, but
worth keeping in mind, since `initiate.md`'s original contradiction-handling flow only
considered ambiguity emerging at the claim level.

## Rough Scope Notes

In scope (rough): locating candidate passages relevant to the approved Research Questions,
within the approved Research Corpus only; capturing exact excerpts with resolvable
provenance and sufficient context; producing a bounded interpretation per passage plus a
short selection rationale explaining why it belongs to the investigation; linking each
candidate evidence item to one or more Research Questions; running the narrow structural/
grounding preflight checks listed above; explicitly reporting when no candidate evidence is
found for a Research Question; recognizing mechanical duplication while preserving
corroboration signal; emitting results as provisional Candidate Evidence pending
acceptance.

Out of scope (rough): any new source discovery, web search, or crawling (stays inside
EA-0003's boundary); the substantive acceptance decision (accept/reject/revise — belongs to
EA-0008, Knowledge Review); contradiction or ambiguity reasoning; claim
construction; reasoning about what corroboration *means* or aggregating corroborating
evidence (a later feature's job — this feature only preserves the distinction from
duplication); canonical ownership of the "Evidence Category" vocabulary term (left
intentionally open per EA-0002, for the same premature-ontology reason).

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (seven listed)
- [x] Suspected dependencies are named (even if marked uncertain)
- [x] No actor+outcome DBA form appears anywhere in this brief
- [x] No stable guarantees or DBA scope boundaries appear in this brief
- [x] The feature can be described without mentioning implementation technology
- [x] (R-type only) — n/a, this is F-type

**Brief status**: READY FOR STAGE 1

---

<!-- METADATA -->
brief_created: 2026-07-17
brief_last_updated: 2026-07-18
stage1_started:
