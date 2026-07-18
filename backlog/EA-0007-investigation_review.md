# Feature Brief: EA-0007 — Investigation Review

**Slug**: investigation_review
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational (governance feature; consumes EA-0001 and EA-0002 directly)
**Status**: BRIEF-DRAFT

---

## Problem / Need

Without a review point for the investigation setup, resources could be spent researching a
poorly-scoped or drifting investigation before any human confirms the Research Brief and
the Research Plan derived from it are actually sound together. The revision discipline
already established in EA-0001 and EA-0002 (Plan v1 → Rejected → Plan v2) has no review
activity attached to it without this feature — it describes what versioning looks like, not
who decides a version needs to happen.

## Primary Actor

The **Editor / Research Lead** — the same role already established in EA-0001 and EA-0002,
not a new name. This feature formalizes the review activity those two briefs already
assumed that actor performs.

## Core Outcome (informal)

The Editor can approve — or decline — the investigation setup (the Research Brief and its
derived Research Plan together) before any resources are spent on evidence collection. This
is one governance phase, not one atomic decision: the Editor can approve the Brief while
separately sending the Plan back for revision, without needing to re-litigate the Brief
itself.

**Proposed artifact:** an Investigation Approval record — the outcome of one review pass,
naming which of the Research Brief and Research Plan were approved, which (if any) were
sent back for revision, and by whom. Exact shape (fields, storage) is Stage 1/2 work; this
brief only proposes that such a record is this feature's output.

## Design Tensions and Open Questions

1. **What are the actual possible outcomes of one review pass?** [Tentative: (a) both
   approved → Corpus Construction may begin; (b) Brief approved, Plan needs revision → a
   new Plan version is produced and only that portion is re-reviewed; (c) Brief itself needs
   revision.]
2. **If the Brief changes, does the existing Plan survive?** [Tentative: no — a revised
   Decision Question most likely invalidates a Plan derived from the old one, so a Brief
   revision probably triggers Plan re-derivation and a fresh review of both. Not fully
   resolved; a minor Brief clarification might not always require this, but treating it as
   "probably yes" is the safer default until evidence says otherwise.]
3. **Blocking, not advisory.** [Resolved as this brief's proposed answer to EA-0002's
   previously open Design Tension #2 — see the corresponding correction note added there.
   Because Plan approval is proposed as part of Investigation Review rather than a
   standalone checkpoint, it is naturally blocking: Corpus Construction is not intended to
   begin until this feature approves, at minimum, the Plan.]
4. **Does every revision require full re-review, or just the changed artifact?** [Tentative:
   just the changed artifact — a Plan v2 triggered by a plan-only rejection likely only
   needs the Plan re-reviewed, not the already-approved Brief; a Brief v2 likely requires
   review of both, per open question #2 above.]

## Suspected Dependencies

Upstream (hard): EA-0001 (Research Brief) and EA-0002 (Research Plan), both consumed
directly and reviewed together as one phase.

Downstream (hard): EA-0003 (Corpus Construction) does not begin until this feature approves
the investigation, at minimum the Plan portion.

## Rough Scope Notes

In scope (rough): reviewing the Research Brief and Research Plan together as one governance
phase; supporting partial approval/rejection outcomes; determining whether a Brief revision
requires re-deriving and re-reviewing the Plan.

Out of scope (rough): deriving the Plan itself (EA-0002's job); any evidence, claim, or
ambiguity review (Knowledge Review's job, EA-0008); corpus-execution decisions, including
the corpus-gap escalation (EA-0003's own exception path, explicitly excluded from this
feature's scope per Architecture Journal AJ-003).

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
