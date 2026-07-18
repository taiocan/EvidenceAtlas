# Feature Brief: EA-0009 — Publication Review

**Slug**: publication_review
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational (governance feature; depends on a not-yet-briefed Publishing
feature and on EA-0008's accepted knowledge base)
**Status**: BRIEF-DRAFT

---

## Problem / Need

Without a final review before publishing, a published view could reach readers even if it
misrepresents the underlying accepted knowledge — presenting a contested claim as settled
fact, omitting a known ambiguity, or drifting from what was actually investigated. That
would undermine the project's "decision support, not truth declaration" principle and the
contested-claim-publication policy already hypothesized during Solution Discovery
(`docs/solution-discovery-evidenceatlas.md` §7).

## Primary Actor

The **Publication Reviewer** — a genuinely new role, distinct from the Knowledge Reviewer
(EA-0008) and the Editor/Research Lead (EA-0007). The review question here is categorically
different — "should this leave the system," an external-facing presentation judgment — not
"can I trust this knowledge" or "is this the right investigation." Unlike Knowledge
Review's actor consolidation, this isn't absorbing an existing name; it's a new judgment
type with no prior equivalent in this pipeline.

## Core Outcome (informal)

The Publication Reviewer can confirm that a proposed published view (Article, Reality
Check, Decision Brief, or future Topic Page) accurately reflects the underlying accepted
knowledge base — including any contested or ambiguous points and their required framing —
before it becomes visible outside the system.

**Proposed artifact:** a Publication Review record per decision — naming which published
view was reviewed, the outcome (approved/returned for revision), and the rationale. Exact
shape is Stage 1/2 work; this brief only proposes that such a record is this feature's
output, one per decision made (added 2026-07-18, so EA-0011 (Review Registry) has a
supported canonical source to aggregate).

## Design Tensions and Open Questions

1. **Does this feature review content/framing decisions, or the final rendered artifact?**
   [Tentative: content and framing correctness — which claims and ambiguities were
   selected, how they're framed, whether required disclosures (e.g. showing opposing
   evidence for a contested claim) are present — not proofreading, formatting, or rendering,
   which belongs to the Presentation Layer.]
2. **Policy-driven enforcement, not hardcoded rules.** [Tentative, consistent with EA-0007
   and EA-0008: this feature consults the not-yet-briefed Policy Registry for publication-
   time rules (e.g. the contested-claim-publication policy) rather than encoding them
   itself.]
3. **Can this feature approve part of a multi-view output and reject another part?**
   [Not resolved — e.g. is the Reality Check sent back for revision while the Article is
   approved, or is it necessarily one judgment across the whole published package for a
   given investigation? Left open.]
4. **Frequency.** [Tentative: once per published view, not once per investigation — since
   the not-yet-briefed Publishing feature is expected to produce multiple distinct views
   (Article, Reality Check, Decision Brief, Topic Page) from the same accepted claims, and
   each serves a different audience/purpose, so each plausibly needs independent review.]

## Suspected Dependencies

Upstream (hard): a not-yet-briefed Publishing feature (produces draft published views from
accepted Claims and Ambiguities) — a forward dependency, similar to how EA-0005 forward-
referenced Claim Construction before it was briefed. Also EA-0008's accepted knowledge base
(Accepted Evidence, Accepted Claims, structured Ambiguities), as the source of truth
published views are checked against. Also a not-yet-briefed Policy Registry, consulted for
publication-time policy enforcement.

Downstream, publication flow: none — this is the last internal checkpoint before external
visibility; what comes after is publication itself, not another pipeline feature.

Downstream, registry consumer: EA-0011 (Review Registry) aggregates this feature's
Publication Review records (added 2026-07-18) — this is a registry relationship, not
another stage in the publication flow itself.

## Rough Scope Notes

In scope (rough): confirming a published view's content and framing accurately reflect the
accepted knowledge base, including required framing for contested or ambiguous points;
consulting the Policy Registry for applicable publication-time policies.

Out of scope (rough): generating the published view itself (the not-yet-briefed Publishing
feature's job); proofreading, formatting, or rendering (Presentation Layer's job);
re-litigating Knowledge Review's own accept/reject decisions, which are already settled by
the time a view reaches this feature.

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (four listed)
- [x] Suspected dependencies are named (even if marked uncertain)
- [x] No actor+outcome DBA form appears anywhere in this brief
- [x] No stable guarantees or DBA scope boundaries appear in this brief (scope notes are
      informal guardrails, not formal DBA contract language)
- [x] The feature can be described without mentioning implementation technology
- [x] (R-type only) — n/a, this is F-type

**Brief status**: READY FOR STAGE 1

---

<!-- METADATA -->
brief_created: 2026-07-17
brief_last_updated: 2026-07-18
stage1_started:
