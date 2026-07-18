# Feature Brief: EA-0013 — Publishing

**Slug**: publishing
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational, last pipeline (Knowledge-transformation) feature. Resolves
Architecture Journal AJ-005's deferred questions about the referencing artifact Dependency
Registry will eventually index.
**Status**: BRIEF-DRAFT

---

## Problem / Need

Accepted Claims and Ambiguities exist, but nothing yet turns them into a purpose-specific
representation for a reader — an Article, a Reality Check, a Decision Brief, or a future
Topic Page all need to select a subset of accepted knowledge, arrange and frame it for a
specific audience and purpose, and preserve exactly which Claim or Ambiguity backs each
part of what's said. Without this, either every view has to be assembled ad hoc with no
consistent framing discipline, or the same reviewed knowledge can't be reused across
multiple views the way `initiate.md` identifies as the project's main source of
scalability.

## Primary Actor

A **Publishing Editor** role, distinct from the Knowledge Reviewer (EA-0008) and Editor/
Research Lead (EA-0001/EA-0002/EA-0007) — the person deciding which accepted Claims and
Ambiguities belong in a given view and how they should be framed for its audience. The
review question differs from every prior role: not "is this fit for acceptance" or "is this
the right investigation," but "does this representation serve its intended purpose and
audience." The same person may fill this role too in v1; noted for Architecture Journal
AJ-002's tally regardless.

## Core Outcome (informal)

The Publishing Editor can produce a structured, reviewable composition — a **Publishing
View Revision** — that selects specific accepted Claims and Ambiguities, frames each one
(fact, interpretation, recommendation, or caveat), and arranges them for a specific view
type, without needing to invent framing conventions from scratch each time or losing track
of which underlying knowledge backs each part of the result.

## Design Tensions and Open Questions

1. **Publishing vs. Presentation.** [Resolved: this feature owns content selection,
   framing, and composition — deciding which Claims/Ambiguities are included and how
   they're framed. Markdown/MDX serialization, HTML/Astro generation, JSON-LD, typography,
   and other rendering concerns are a separate, downstream concern (Presentation), out of
   scope here. Publication Review (EA-0009) reviews the structured composition this feature
   produces, not the rendered output — keeping content correctness from getting entangled
   with rendering.]
2. **One feature for all view types, not one per type.** [Resolved: Article, Reality Check,
   Decision Brief, and future Topic Page share substantial behavior — consuming accepted
   knowledge, selecting a subset, framing and arranging it, preserving provenance,
   supporting revision and lifecycle. What differs is composition policy per view type
   (e.g. an Article emphasizes narrative, a Decision Brief separates evidence/assumptions/
   options/recommendations), not the underlying transformation. Splitting into four
   features would duplicate the lifecycle, reference model, and review relationship for no
   real gain.]
3. **What is the canonical referencing artifact, resolving AJ-005?** [Resolved: the
   **Publishing View Revision** — not the abstract Publication, and not the rendered
   output. A Publication is a stable identity across its lifetime (e.g. "EU Battery
   Regulation: Strategic Implications"); each Publishing View Revision is an immutable
   content composition at a point in time, and is the artifact that actually carries
   Claim/Ambiguity references. Rendered output is a separate, mechanical projection of one
   approved revision — not itself a source of dependency truth.]
4. **Explicit references, never inferred.** [Resolved: every use of a Claim or Ambiguity
   must be represented explicitly and structurally within the revision itself — never
   inferred later by scanning rendered prose. This is what makes reliable impact analysis,
   correction, and withdrawal possible.]
5. **Can one revision reference both Claims and Ambiguities?** [Resolved: yes, and often
   must — publishing a contested Claim without its accompanying Ambiguity would risk
   exactly the misrepresentation EA-0009 exists to prevent. Claims and Ambiguities stay
   distinguishable roles within a revision, not flattened into one undifferentiated list.]
6. **What granularity do references attach at?** [Resolved in principle, not in exact
   vocabulary: references attach to structured **content units** within a revision (e.g.
   something like a section, an evidence block, a recommendation, a caveat — illustrative,
   not a locked taxonomy), with revision-level and publication-level dependency views
   derived from those. A flat whole-view reference list is too coarse — if a Claim changes,
   the editor needs to know where and for what purpose it was used, not just that some
   article somewhere cites it. The specific content-unit typology is left to Stage 1/2, to
   avoid the same premature-ontology problem already avoided twice for "Evidence
   Category."]
7. **Do revisions replace or coexist?** [Resolved: coexist. A revision is immutable once
   created; a newer revision can supersede an older one, but never erases or rewrites it.
   Each revision retains its own references, so both "what does the current revision depend
   on" and "what did an earlier revision depend on" stay answerable — this is what keeps
   the eventual Dependency Registry's history honest rather than lossy.]
8. **Lifecycle ownership.** [Resolved in principle: this feature owns the Publication's and
   its revisions' lifecycle (creating drafts, producing revisions after requested changes,
   marking a reviewed revision published, superseding, withdrawing) — but never the
   approval decision itself, which stays exclusively EA-0009's. **The exact state model is
   tentative, not settled** — something like Draft → Under Review → Approved → Published →
   Superseded, with Withdrawn reachable from Approved or Published, is a reasonable
   candidate, and keeping Approved and Published as distinct states (approval means the
   content is acceptable; published means it's actually externally active) is worth
   preserving since it supports scheduled/embargoed release without making EA-0009
   responsible for the operational act of publishing. Needs Stage 1/2 to confirm the actual
   states and transitions, consistent with how every other lifecycle in this project has
   been treated.]
9. **How much history does this feature retain?** [Resolved: all of it. Draft, superseded,
   and withdrawn revisions are never discarded — only a full revision history lets the
   eventual Dependency Registry answer both "what do currently published revisions depend
   on" and "has this Claim ever appeared in any public output." What query views Dependency
   Registry exposes over that history is that feature's own scope to define, not this one's.]

## Suspected Dependencies

Upstream (hard): EA-0008's accepted knowledge base (Accepted Evidence indirectly, Accepted
Claims and Ambiguities directly) — this feature composes from what Knowledge Review has
already accepted, never from Candidate-stage material.

Downstream (hard): EA-0009 (Publication Review) consumes Publishing View Revisions
directly and owns the approve/reject/request-revision decision on them — this feature must
never self-approve.

Downstream (soft, forward): the not-yet-briefed Dependency Registry will index this
feature's structured Claim/Ambiguity references across all revisions; a separate,
not-yet-briefed Presentation capability will render an approved revision into Markdown/MDX/
HTML/Astro output — not yet confirmed as a domain feature versus a purely technical
capability.

## Rough Scope Notes

In scope (rough): selecting accepted Claims and Ambiguities for a given view type;
composing and framing them into structured content units; producing an immutable Publishing
View Revision with explicit references; owning Publication/revision identity and lifecycle
(draft, revision, published, superseded, withdrawn) short of the approval decision itself.

Out of scope (rough): accepting or rejecting knowledge (EA-0008's job); approving
publication correctness (EA-0009's job); rendering technology, layout, or typography
(Presentation's job, once/if briefed); inferring dependencies from rendered prose;
dependency reverse-indexing itself (the not-yet-briefed Dependency Registry's job); a fixed
content-unit taxonomy (left to Stage 1/2).

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (nine listed; most resolved as principles, #6 and
      #8 explicitly flagged as needing Stage 1/2 confirmation rather than settled)
- [x] Suspected dependencies are named (even if marked uncertain)
- [x] No actor+outcome DBA form appears anywhere in this brief
- [x] No stable guarantees or DBA scope boundaries appear in this brief (the lifecycle and
      content-unit descriptions are proposed design candidates for Stage 1/2, not approved
      DBA contracts)
- [x] The feature can be described without mentioning implementation technology
- [x] (R-type only) — n/a, this is F-type

**Brief status**: READY FOR STAGE 1

---

<!-- METADATA -->
brief_created: 2026-07-18
brief_last_updated: 2026-07-18
stage1_started:
