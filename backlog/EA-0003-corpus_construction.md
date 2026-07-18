# Feature Brief: EA-0003 — Corpus Construction

**Slug**: corpus_construction
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational (third domain feature; depends only on EA-0002)
**Status**: BRIEF-DRAFT

---

## Problem / Need

The problem is not finding sources — it's constructing a corpus that faithfully implements
the approved Research Plan. Without this, sources get gathered, but nobody knows whether
the required viewpoints were actually represented, duplicate evidence overwhelms unique
evidence, coverage of the plan can't be assessed, and evidence quality varies
unpredictably from one investigation to the next.

## Primary Actor

The Editor / Research Lead — the same role as EA-0001/EA-0002. They need confidence that
the collected corpus adequately represents the planned investigation before evidence
extraction begins. They may not inspect every document, but they are the consumer of the
resulting assessment of how the plan was actually executed.

## Core Outcome (informal)

The Editor can understand how completely the approved investigation was executed, what
evidence was successfully obtained, what remains missing, and why. The value isn't "I have
a corpus" — nobody wants a corpus for its own sake — it's "I understand whether this corpus
is an adequate foundation for evidence extraction, including any known limitations that
could materially affect downstream conclusions." Adequate deliberately does not mean
complete.

## Design Tensions and Open Questions

1. Is Corpus Construction optimizing for evidence quality or investigation completeness?
   [Resolved as a principle: optimize for plan fulfillment, and report quality
   characteristics rather than silently filtering required perspectives away. A mediocre
   but genuinely opposing source shouldn't be dropped on quality grounds if the plan
   required that perspective — quality becomes information attached to the corpus, not a
   silent filtering policy.]
2. Should this feature notice contradictions between sources? [Resolved: no. It reports only
   structural properties — perspective found, perspective missing, source duplicated,
   retrieval failed. Judging that two studies actually contradict each other requires
   interpreting evidence, which belongs to a later, not-yet-briefed feature.]
3. Does this feature ever decide an incomplete corpus is "acceptable"? [Resolved as a
   principle: never. It only determines whether the Plan has been satisfied as far as
   practical and reports the gaps. What happens next — block, proceed with documented gaps,
   or escalate to the editor — is deliberately deferred to a later feature or architectural
   decision, since different operating modes may legitimately want different behavior. This
   is also tracked under Architecture Journal AJ-001.]
4. If the Research Brief is revised after corpus construction has started, does the corpus
   update incrementally or restart? [Resolved: restart — Brief v2 → Plan v2 → Corpus v2, no
   incremental mutation of a corpus already in progress, to keep provenance intact.]
5. Within the resulting **Research Execution Report** (renamed from an earlier "Coverage
   Assessment" framing — coverage is only one dimension of whether execution actually
   succeeded), which information should stay execution-local versus travel downstream to
   later features? [Tentative split: *operational telemetry* — retrieval timestamps, retry
   counts, download failures, API errors — stays local to this feature. *Evidence-base
   characteristics* — missing planned perspectives, an unusually sparse corpus, a skewed
   quality distribution — should remain visible downstream, since they give later features
   context for confidence assessment without requiring this feature to interpret evidence
   itself. **One open nuance, not fully resolved:** "stopping reason" (e.g. "plan fully
   satisfied" vs. "ran out of budget" vs. "no further sources existed") carries real weight
   for how much to trust the corpus's completeness — closer to an evidence-base
   characteristic than to pure operational telemetry like a retry count. Recorded here as
   evidence-base-characteristic (downstream-visible) pending Stage 1/2 confirmation.]

## Suspected Dependencies

Upstream: EA-0002 (Research Plan) only.

Downstream (hard): the next, not-yet-briefed feature (Evidence Extraction) consumes both
the Research Corpus and the Research Execution Report directly.

Downstream (soft): Claim Construction and/or the Contradiction Resolution Workflow may want
the Execution Report's evidence-base characteristics (missing perspectives, sparse
coverage, quality distribution, stopping reason) as context for confidence assessment —
without this feature making any interpretive judgment itself. Purely operational telemetry
(retrieval duration, retry counts, raw error codes) shouldn't need to travel that far.

## Rough Scope Notes

In scope (rough): discovering sources per the approved Plan; mechanical deduplication;
structural coverage measurement against required perspectives; producing a Research Corpus
plus a Research Execution Report (coverage assessment, retrieval outcomes, known gaps,
quality signals, stopping reason, execution summary).

Out of scope (rough): evidence interpretation, claim construction, or contradiction
judgment (all later features); deduplication *policy* decisions beyond mechanical dedup;
source credibility judgment beyond whatever objective quality signals are defined for
assembly; deciding that a required perspective "doesn't matter anymore" — that's an
interpretation, not an execution fact.

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (five listed)
- [x] Suspected dependencies are named (even if marked uncertain)
- [x] No actor+outcome DBA form appears anywhere in this brief
- [x] No stable guarantees or DBA scope boundaries appear in this brief
- [x] The feature can be described without mentioning implementation technology
- [x] (R-type only) — n/a, this is F-type

**Brief status**: READY FOR STAGE 1

---

<!-- METADATA -->
brief_created: 2026-07-17
brief_last_updated: 2026-07-17
stage1_started:
