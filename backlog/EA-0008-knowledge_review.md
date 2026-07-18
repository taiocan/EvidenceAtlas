# Feature Brief: EA-0008 — Knowledge Review

**Slug**: knowledge_review
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational (governance feature; consumes EA-0004, EA-0005, and EA-0006
directly, and recurs across the pipeline rather than firing once)
**Status**: BRIEF-DRAFT

---

## Problem / Need

Without a way to evaluate whether extracted evidence, synthesized claims, and structured
ambiguities actually represent trustworthy knowledge, unreviewed or possibly-hallucinated
material could silently enter the pipeline and eventually reach publication. The entire
evidence-first premise of this project depends on a real checkpoint existing between "the
AI produced a candidate" and "this is part of the trusted knowledge base" — right now
three separate transformation features (EA-0004, EA-0005, EA-0006) each assume that
checkpoint exists without any feature actually owning it.

## Primary Actor

The **Knowledge Reviewer** — a single role that replaces the separately-named "Evidence
Reviewer," "Ambiguity Reviewer," and "Claim Reviewer" used when EA-0004, EA-0005, and
EA-0006 were briefed (those briefs are being corrected to reflect this consolidation). The
underlying review question still differs by what's under review — is this excerpt and
interpretation faithful to its source; is this synthesis adequately supported, bounded, and
decision-relevant; does this structure a genuine, decision-relevant disagreement — but it's
one role asking variants of one broader question: can this be trusted as part of the
knowledge base.

## Core Outcome (informal)

The Knowledge Reviewer can evaluate a proposed piece of knowledge — Candidate Evidence, a
Candidate Claim, or a constructed Ambiguity — without needing to re-derive or reconstruct
the underlying material or reasoning themselves, since the feature that produced it has
already prepared it for review (excerpt plus interpretation and rationale; synthesis with
supporting/limiting evidence attached; structured competing positions with their evidence).
This is a recurring governance activity applied at multiple points across the pipeline as
material arrives, not a single point-in-time gate.

**Proposed artifact:** a Knowledge Review record per decision — naming which artifact was
reviewed (Candidate Evidence, Candidate Claim, or Ambiguity), the outcome
(accept/reject/return-for-revision), and the rationale. Exact shape is Stage 1/2 work; this
brief only proposes that such a record is this feature's output, one per decision made
(added 2026-07-18, so EA-0011 (Review Registry) has a supported canonical source to
aggregate).

## Design Tensions and Open Questions

1. **This is recurring, not a single gate.** [Resolved, per Architecture Journal AJ-003:
   this feature fires repeatedly — once evidence is extracted, once claims are synthesized,
   once ambiguities are constructed — under one policy umbrella, rather than being one
   checkpoint that happens once per investigation.]
2. **Does this feature own the accept/reject/return-for-revision decisions previously
   assumed by EA-0004 and EA-0006?** [Resolved: yes. This is where those "assumptions
   requiring validation" become owned decisions — accept/reject/revise on Candidate
   Evidence; accept/reject/revise on Candidate Claims; accept/return-for-more-analysis on
   constructed Ambiguities. This feature also owns routing a human-initiated suspected-
   disagreement referral to EA-0005 (previously described as something "Gate 1" did in
   EA-0004's brief).]
3. **Does review of one artifact type block progress on others?** [Not resolved — must all
   evidence for a Research Question be accepted before Claim Construction can run on any of
   it, or can synthesis proceed incrementally as evidence is accepted in batches? A genuine
   open question for Stage 1/2, not decided here.]
4. **Granularity and blocking-vs-advisory are policy-driven, not structural.** [Resolved,
   per AJ-003 and the discovery doc's "Policy centralization" finding: this feature consults
   a not-yet-briefed Policy Registry for review strategy (per-item, per-bundle, sampled,
   blocking, advisory, risk-based skipping) rather than hardcoding one strategy for every
   artifact type.]

## Suspected Dependencies

Upstream (hard): EA-0004 (Candidate Evidence), EA-0005 (constructed Ambiguities), and
EA-0006 (Candidate Claims) — all three consumed directly. Also a not-yet-briefed Policy
Registry feature, consulted for review strategy — recorded as a belief, not yet verified.

Note on relationship shape: this is not a simple one-directional consumption. This
feature's Accepted Evidence output feeds EA-0006 (Claim Construction), which produces
Candidate Claims that come back to this same feature for review — a recurring, staged
back-and-forth across the pipeline, not a cycle within a single pass.

Downstream (hard): EA-0006 depends on this feature's Accepted Evidence output (per the
correction already made to EA-0004's brief).

Downstream (soft): eventual Publishing views and EA-0009 (Publication Review, once briefed)
will likely consume this feature's accepted knowledge base (Accepted Evidence, Accepted
Claims, resolved Ambiguities) as their source of truth.

## Rough Scope Notes

In scope (rough): evaluating Candidate Evidence, Candidate Claims, and Ambiguities for
trustworthiness, using the distinct question appropriate to each; owning accept/reject/
return-for-revision outcomes for each; routing human-initiated disagreement referrals to
Ambiguity Construction; consulting the Policy Registry for review strategy.

Out of scope (rough): producing any of the underlying candidates itself (each transformation
feature's own job); investigation-level approval (EA-0007's job); publication-level approval
(EA-0009's job, once briefed); defining the Policy Registry itself.

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
