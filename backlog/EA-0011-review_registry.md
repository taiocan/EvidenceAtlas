# Feature Brief: EA-0011 — Review Registry

**Slug**: review_registry
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational, third member of the shared infrastructure layer beneath the
pipeline. Per Architecture Journal AJ-006, this is a **Derived Ledger** — a distinct
sub-class from Policy Registry's **Authority** role and Dependency Registry's **Index**
role. It authors nothing itself; it aggregates records the governance features already
produce.
**Status**: BRIEF-DRAFT

---

## Problem / Need

EA-0007, EA-0008, and EA-0009 each make governance decisions and each will produce their
own canonical record of those decisions — but without a unified place to look, answering a
question like "what review history exists for this investigation" or "who approved this
Claim, and when" requires separately querying three different places and manually merging
the results by correlation. That's exactly the audit-trail gap `initiate.md` originally
named this registry to close.

## Primary Actor

The **Editor / Research Lead** — not as an author of review records (those are owned
exclusively by EA-0007/EA-0008/EA-0009), but as the person who needs to reconstruct
governance history: what was decided, by what rationale, and when, across an investigation
or across the whole knowledge base.

## Core Outcome (informal)

The Editor can look in one place to answer "what review decisions exist, in what order,
with what rationale" for a given investigation, artifact, or reviewer — without needing to
separately query Investigation Review, Knowledge Review, and Publication Review and merge
the results by hand. This feature adds no new judgment of its own; it only makes existing
judgments visible together.

## Design Tensions and Open Questions

1. **This is a Derived Ledger, not an authoring feature.** [Resolved, per AJ-006: EA-0007,
   EA-0008, and EA-0009 each own authoring their own canonical decision record. This
   feature introduces no new authoring workflow and no business logic — it aggregates.]
2. **Immutability.** [Resolved: entries in this ledger are never edited, only appended to.
   A correction is a new entry referencing the old one, never a rewrite — the same
   append-only Decision Log discipline already established in `dba-system.md`, and the same
   pattern this project's own `reviews/review-log.md` has used all session.]
3. **Does Policy Registry's (EA-0010) change history belong in this same ledger, or stay
   separate?** [Not resolved. EA-0010 said policy changes are "versioned and auditable" but
   never specified where that history lives. Policy edits aren't quite the same kind of
   thing as an Investigation/Knowledge/Publication Review decision — they're operational
   configuration changes, not epistemic governance calls — so unifying them here isn't
   obviously right, but keeping two separate audit trails isn't obviously right either.
   Left for Stage 1/2.]
4. **Does EA-0003's corpus-gap escalation belong here?** [Not resolved. AJ-003 explicitly
   excluded that decision from the governance-checkpoint count (it's operational exception
   handling, not a trust judgment) — but when a human does make that call, should it still
   be logged in this ledger for audit purposes, or does it fall outside this registry's
   scope entirely since it isn't one of the three AJ-003 governance classes? Left open.]

## Suspected Dependencies

Upstream (hard): EA-0007 (Investigation Approval records), EA-0008 (Knowledge Review
records), EA-0009 (Publication Review records) — all three are canonical sources this
feature aggregates, not derives independently.

Downstream (soft): the Editor/Research Lead, for reconstructing governance history; possibly
a future audit or compliance-facing view, not yet needed for v1.

Related, not yet resolved (see Design Tensions #3-4): EA-0010 (Policy Registry)'s change
history, and EA-0003's corpus-gap escalation.

## Rough Scope Notes

In scope (rough): aggregating the canonical review records from EA-0007/EA-0008/EA-0009
into one append-only, queryable ledger; supporting queries by investigation, artifact, or
reviewer; preserving full history with no edits to existing entries.

Out of scope (rough): authoring or making any review decision itself (exclusively owned by
the three governance features); any business logic beyond aggregation and querying; the
canonical event log for state changes generally (a broader concern for the not-yet-briefed
Change Event Registry to resolve against this one, per Architecture Journal AJ-006).

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (four listed; #1-2 resolved as principles, #3-4
      genuinely open)
- [x] Suspected dependencies are named (even if marked uncertain)
- [x] No actor+outcome DBA form appears anywhere in this brief
- [x] No stable guarantees or DBA scope boundaries appear in this brief (the append-only/
      no-edit property in Design Tension #2 is a proposed design principle for Stage 1/2 to
      formalize, not an already-implemented or approved DBA guarantee)
- [x] The feature can be described without mentioning implementation technology
- [x] (R-type only) — n/a, this is F-type

**Brief status**: READY FOR STAGE 1

---

<!-- METADATA -->
brief_created: 2026-07-18
brief_last_updated: 2026-07-18
stage1_started:
