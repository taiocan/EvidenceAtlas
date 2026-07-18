# Feature Brief: EA-0014 — Dependency Registry

**Slug**: dependency_registry
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational, the shared infrastructure layer's first (and so far only)
**Derived Index**, per Architecture Journal AJ-005. Its briefing was deliberately deferred
until EA-0013 established the canonical referencing artifact.
**Status**: BRIEF-DRAFT

---

## Problem / Need

A Claim or Ambiguity has no way of knowing in advance which Publishing View Revisions will
reference it. Without a reverse lookup, correcting a Claim, accepting a new Ambiguity, or
withdrawing a publication all require manually searching every revision ever produced to
find what's actually affected — which doesn't scale and risks silently missing an affected
publication.

## Primary Actor

The **Editor / Research Lead** — the same role used throughout the infrastructure layer,
performing publication impact analysis rather than authoring index data. This role queries
the index; it does not populate it. Impact analysis is an activity this person already
naturally performs while maintaining the knowledge and publication estate, not evidence of
a distinct role — consistent with how Architecture Journal AJ-004 has treated actor
naming across this layer.

## Core Outcome (informal)

The Editor can ask, in one place, which Publishing View Revisions — across any lifecycle
state — reference a given Claim or Ambiguity, and get an answer grounded in explicit,
structured references rather than a manual search through rendered content. This feature
authors nothing; it mechanically projects relationships that already exist on Publishing
View Revisions (EA-0013) into a queryable reverse view.

## Design Tensions and Open Questions

1. **Classification.** [Resolved, per AJ-005: a Derived Index. It performs no epistemic
   transformation, interpretation, or synthesis — only a mechanical reverse projection of
   relationships already owned by Publishing View Revisions.]
2. **Query scope — semantic dimensions, not a frozen API.** [Resolved: the brief names the
   classes of questions this feature must support, leaving the exact query contract to
   Stage 1/2. Required outcomes include: which currently-published revisions reference this
   Claim; whether this Claim has ever appeared in any public output, including superseded
   or withdrawn revisions; which draft or under-review revisions reference this Ambiguity;
   which historical (superseded/withdrawn) revisions referenced a given Claim or Ambiguity.
   The
   underlying dimensions, established by EA-0013, are: referenced artifact, publication,
   publishing view revision, view type, content unit, lifecycle state, and current-vs-
   historical use. Exact filters, operators, pagination, API/UI shape, and performance
   characteristics are explicitly left to Stage 1/2.]
3. **Scope boundary — strictly the reverse projection, not a general relationship graph.**
   [Resolved, reconfirmed now that EA-0013 exists: this feature covers only
   `Claim/Ambiguity → referenced by → Publishing View Revision content unit`, and the
   derived roll-ups from content-unit usage to revision usage to publication usage. It is
   explicitly **not** the canonical home for Research Question → Evidence, Claim →
   Evidence, or Ambiguity → Claims/Evidence relationships — those stay on the artifacts
   that already own them. This exclusion is stated explicitly because "Dependency
   Registry" is a broad enough name that, without a firm boundary, it could otherwise
   absorb every relationship in the model and become an accidental knowledge graph.]
4. **Revision history is additive, never overwritten.** [Resolved, following directly from
   EA-0013's immutable-revision model: a new Publishing View Revision adds a new dependency
   set; it never overwrites the dependency history of an earlier revision. This gives the
   index stable historical meaning, consistent with the append-only discipline used
   elsewhere in this layer, even though the index itself is a derived projection rather
   than a ledger.]
5. **Does this index need to reflect the referenced Claim's or Ambiguity's own lifecycle,
   not just the Publishing-side one?** [Not resolved — genuinely open. Architecture Journal
   AJ-008 noted that no feature yet owns transitioning an accepted Evidence, Claim, or
   Ambiguity into "challenged," "superseded," or "retired" states — of those, only Claims
   and Ambiguities are ever directly referenced by a Publishing View Revision (per EA-0013),
   so only their lifecycle would matter here; Evidence would only ever affect this index
   indirectly, through a Claim it supports, never as a direct reference. If AJ-008's gap is
   later resolved for Claims/Ambiguities, this feature will likely need to answer questions
   like "which published revisions reference a Claim that has since been challenged" —
   combining the Publishing-side lifecycle with the referenced artifact's own lifecycle.
   Not decided here; left for when AJ-008 is addressed.]

## Suspected Dependencies

Upstream (hard): EA-0013 (Publishing) is the sole canonical source of the structured,
content-unit-level Claim/Ambiguity references this feature projects. This feature neither
authors nor becomes the canonical owner of those relationships — it only projects them.

Downstream (soft): the Editor/Research Lead, for impact analysis, correction, and
withdrawal workflows. A future compliance or audit-facing consumer is plausible but not a
v1 driver of this feature's boundary.

Related, not yet resolved (see Design Tension #5): Architecture Journal AJ-008's
unaddressed post-acceptance lifecycle-ownership gap.

## Rough Scope Notes

In scope (rough): deriving a reverse lookup from Publishing View Revisions' structured
references; supporting queries across the semantic dimensions named above (referenced
artifact, publication, revision, view type, content unit, lifecycle state, current vs.
historical); preserving visibility of the full immutable revision history, with each new
revision contributing a distinct dependency set and no earlier revision's dependencies
being replaced.

Out of scope (rough): authoring or maintaining any canonical relationship itself (owned
exclusively by the artifacts that hold them); becoming a general-purpose relationship graph
covering Research-Question→Evidence, Claim→Evidence, or Ambiguity→Claims/Evidence links;
the exact query contract, API/UI shape, filters, or performance characteristics (Stage 1/2
work); resolving AJ-008's lifecycle-ownership gap.

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (five listed; #1-4 resolved as principles, #5
      genuinely open)
- [x] Suspected dependencies are named (even if marked uncertain)
- [x] No actor+outcome DBA form appears anywhere in this brief
- [x] No stable guarantees or DBA scope boundaries appear in this brief (the query-scope
      and additive-history descriptions are proposed design principles for Stage 1/2 to
      formalize, not approved DBA contracts)
- [x] The feature can be described without mentioning implementation technology
- [x] (R-type only) — n/a, this is F-type

**Brief status**: READY FOR STAGE 1

---

<!-- METADATA -->
brief_created: 2026-07-18
brief_last_updated: 2026-07-18
stage1_started:
