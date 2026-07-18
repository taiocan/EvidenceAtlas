# Feature Brief: EA-0012 — Change Event Registry

**Slug**: change_event_registry
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational, second member of the Ledgers sub-class (alongside EA-0011,
Review Registry) within the shared infrastructure layer. Per Architecture Journal AJ-007,
this feature's central dependency — canonical domain events emitted by other features — is
deliberately left unresolved here, not assumed, and is this feature's own future work to
establish.
**Status**: BRIEF-DRAFT

---

## Problem / Need

No feature in this project currently commits to recording its own state transitions beyond
the governance decisions Review Registry already aggregates. Without a single ledger of
domain-significant state transitions — including the ones no human ever reviewed, like a
Corpus Construction run completing or a policy being activated — questions like "what
happened to this investigation, in order" can't be answered, and change-impact analysis
("this claim just became contested, what needs to be reconsidered") has no reliable history
to work from.

## Primary Actor

The **Editor / Research Lead** — consistent with Review Registry and the rest of the
infrastructure layer. The person who needs to reconstruct what happened across an
investigation's full lifecycle, not only the parts a human happened to review.

## Core Outcome (informal)

The Editor can look in one place to answer "what domain-significant things happened, in
what order" across an investigation — including state transitions that never required
human review — without reconstructing that history from each feature's own internal state.

## Design Tensions and Open Questions

1. **Is this a second Ledger, not a fourth infrastructure archetype?** [Resolved, per
   AJ-007: yes. Alongside Review Registry (governance decisions), this is the second
   Ledger — distinguished by *what* is preserved (domain state transitions vs. human
   governance decisions with rationale), not by a different underlying mechanism. Both
   follow the same invariant: no ledger may invent its own canonical records; each
   aggregates records authored elsewhere.]
2. **Central dependency, deliberately unresolved:** this feature assumes upstream features
   emit canonical domain events for their own state transitions. **No feature currently
   does this.** Naming specific events (what exactly EA-0004 or EA-0006 would emit) is
   Stage 3 Event Schema work, not Feature Brief work, per `dba-system.md`'s own doctrine
   ("the most constraining artifact — implementation is locked to it"). This brief
   establishes the requirement that such events must exist somewhere for this feature to
   have anything to aggregate; it does not invent them.
3. **Overlap with Review Registry:** a governance decision (e.g. "Claim Y accepted")
   typically *causes* a state transition (Claim Y: Candidate → Accepted) — does this
   feature duplicate what Review Registry already records? [Tentative: no true
   duplication. Review Registry preserves the decision and its rationale
   (governance-level detail); this feature preserves the raw state-transition fact
   (domain-level detail), including transitions with no governance decision behind them at
   all. Some events will have a corresponding review record; many won't.]
4. **What counts as "domain-significant" enough to warrant an event, versus noise?** [Not
   resolved. Tentative guardrail: domain-significant state transitions (investigation
   approved, evidence accepted, publication withdrawn, policy activated), not incidental
   field-level edits (a description field changed). The exact boundary is later work for
   this feature, informed by the event inventory named in Suspected Dependencies below.]

## Suspected Dependencies

Upstream (hard, unresolved — the central gap this brief exists to make explicit): canonical
domain events from every feature whose state transitions matter. EA-0002 through EA-0010
are all candidate emitters; none currently define what they would emit. This is not treated
as satisfied — it's the open dependency this brief is built around.

Downstream (soft): the Editor/Research Lead, for reconstructing full investigation history;
possibly a future change-impact-analysis capability that needs "what changed and when" as
an input — not yet briefed.

## Rough Scope Notes

In scope (rough): aggregating domain-significant events already emitted elsewhere into one
append-only, queryable ledger, ordered and attributable to the emitting feature; supporting
queries by investigation, artifact, or event type.

Out of scope (rough): deciding what counts as a domain-significant event for any specific
feature (each feature's own later work); authoring or emitting events itself; the specific
event inventory (a follow-on objective for this feature — see Architecture Journal AJ-007 —
not resolved in this brief); duplicating Review Registry's governance-decision-with-
rationale detail.

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (four listed; #1 resolved as a principle, #2-4
      genuinely open — #2 deliberately so, per AJ-007)
- [x] Suspected dependencies are named (even if marked uncertain — #2's upstream dependency
      is explicitly marked unresolved rather than assumed satisfied)
- [x] No actor+outcome DBA form appears anywhere in this brief
- [x] No stable guarantees or DBA scope boundaries appear in this brief (the ledger
      invariant is a proposed cross-feature principle for Stage 1/2 to formalize, not an
      already-approved DBA guarantee)
- [x] The feature can be described without mentioning implementation technology
- [x] (R-type only) — n/a, this is F-type

**Brief status**: READY FOR STAGE 1

---

<!-- METADATA -->
brief_created: 2026-07-18
brief_last_updated: 2026-07-18
stage1_started:
