# Feature Brief: EA-0002 — Research Planning

**Slug**: research_planning
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational (second domain feature; depends only on EA-0001)
**Status**: BRIEF-DRAFT

---

## Problem / Need

Without explicit research planning, an investigation has no explicit strategy: important
perspectives get discovered accidentally, search coverage depends on whatever a search
engine happens to surface, evidence gaps can't be recognized because nobody anticipated
them, and two researchers handed the same Research Brief could end up investigating
completely different things. The Research Brief defines the decision problem; nothing
today defines what evidence must exist before that problem can be answered responsibly.

## Primary Actor

The Editor / Research Lead — the same role from EA-0001. Here they review and approve the
proposed investigation strategy (represented by the Research Plan) before any resources are
spent collecting evidence. The actor is defined by who receives the value (confidence in
the strategy before spending), not by who does the reasoning that produces the plan.

## Core Outcome (informal)

The Editor can evaluate whether the proposed investigation is capable of answering the
original decision question before committing resources to evidence collection. Success is
not "the plan looks reasonable" — it's confidence that, if this plan is executed
successfully, the resulting corpus *should* be sufficient to answer the decision question
within the agreed scope and constraints. Planning never guarantees the outcome; it
guarantees intentionality — that the investigation was designed on purpose rather than
discovered by accident.

## Design Tensions and Open Questions

1. Is Research Planning rule-driven (a fixed checklist of perspective types — academic,
   regulatory, vendor, critical) or question-driven (perspectives derived by reasoning
   about *this specific* decision question)? [Tentative: question-driven. A fixed taxonomy
   just relocates the ontology problem EA-0001 deliberately avoided one feature downstream —
   "should hospitals adopt federated learning" and "should AMD acquire Company X" need
   structurally different investigations, not the same checklist.]
2. Should editor approval of the Research Plan be a hard blocking gate before Corpus
   Construction can start, or advisory? **[Resolved, 2026-07-18, per Architecture Journal
   AJ-003:** progress beyond the investigation-setup phase is blocked until Investigation
   Review (EA-0007) approves the required artifacts — this feature does not itself gate
   anything; the governance responsibility belongs entirely to EA-0007, which reviews the
   Research Brief and this feature's Research Plan together as one phase.]
3. If the editor rejects a plan, is it revised in place, or does that produce a new version?
   [Tentative: new version — Plan v1 → Rejected → Plan v2, mirroring EA-0001's
   revision-not-edit pattern, so it stays possible to know which plan version produced
   which corpus.]
4. Can Research Planning restart after Corpus Construction has already begun? [Tentative:
   only explicitly, never silently. A changed Decision Question produces Brief v2 → Plan v2
   → Corpus v2 — planning must never mutate under an executing corpus.]
5. Should individual Research Questions carry a stable identifier so downstream evidence,
   claims, and eventual Decision Brief content can trace back to which question motivated
   collecting them, and ultimately back to the Decision Question itself? [Not required for
   this feature or for EA-0003 to function — flagged as a forward-looking design
   expectation later features will likely need, not a dependency this feature has today.]

## Suspected Dependencies

Upstream: EA-0001 (Research Brief) only.

Downstream (hard): EA-0003 (Corpus Construction) consumes the Research Plan's Perspectives,
Coverage Goals, Stopping Criteria, and Research Questions directly — and normatively, not
just structurally. The plan defines what "successfully executed" even means for EA-0003.

Downstream (soft, traceability): not required for EA-0003 to function, but later features
(Evidence Extraction, Claim Construction, an eventual Decision Brief) will likely want to
trace a piece of evidence or claim back to the specific Research Question that motivated
seeking it. This is a forward-looking design property worth keeping in mind, not a
functional dependency this feature carries today.

## Rough Scope Notes

In scope (rough): deriving Research Questions, required perspectives, and stopping criteria
from an approved Research Brief; producing one reviewable Research Plan.

Out of scope (rough): query execution or actual searching/retrieval (that's EA-0003);
source ranking, retrieval optimization, search-query tuning, or cost optimization (all
execution concerns); a fixed/hardcoded perspective-type taxonomy; plan versioning or
comparison beyond a simple reject-and-revise cycle.

**Note (intentionally undecided):** ownership of "Evidence Category" as a canonical
vocabulary term is left open on purpose — it may belong to evidence modeling (a later,
not-yet-briefed feature) rather than to Planning. Planning may reference categories without
owning their canonical definition; forcing that decision now risks the same premature-
ontology problem this brief is otherwise avoiding.

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (five listed)
- [x] Suspected dependencies are named (even if marked uncertain)
- [x] No actor+outcome DBA form appears anywhere in this brief
- [x] No stable guarantees or DBA scope boundaries appear in this brief (the
      investigation-setup blocking rule is a cross-feature governance note owned by
      EA-0007, not a formal DBA contract stated by this feature)
- [x] The feature can be described without mentioning implementation technology
- [x] (R-type only) — n/a, this is F-type

**Brief status**: READY FOR STAGE 1

---

<!-- METADATA -->
brief_created: 2026-07-17
brief_last_updated: 2026-07-18
stage1_started:
