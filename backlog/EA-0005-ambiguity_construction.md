# Feature Brief: EA-0005 — Ambiguity Construction

**Slug**: ambiguity_construction
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational (depends on EA-0004 directly; EA-0006, briefed after this
feature, supplies its second input path — see Suspected Dependencies)
**Status**: BRIEF-DRAFT

---

## Problem / Need

Evidence — and eventually claims — bearing on the same Research Question can embody
genuinely incompatible positions. Without a way to structure that disagreement explicitly,
the pipeline either forces a single conclusion that quietly discards a real, decision-
relevant dispute, or loses track of the disagreement entirely because nothing ever recorded
it. Both failure modes undermine the "preserve uncertainty, don't hide it" principle this
project exists to uphold.

## Primary Actor

**Correction (2026-07-18, per Architecture Journal AJ-003):** the actor for this feature is
the **Knowledge Reviewer** — the same unified role used for EA-0004 and EA-0006 (this
section previously named a standalone "Ambiguity Reviewer"; that name is retired). The
question the Knowledge Reviewer asks here is specifically whether a proposed Ambiguity
accurately structures a real, decision-relevant disagreement — including the competing
positions, the evidence behind each, and the conditions that distinguish them — a different
question from evidence acceptance or claim approval, but asked by the same role rather than
a separate actor. (Tracked in Architecture Journal AJ-002.)

## Core Outcome (informal)

The Knowledge Reviewer can evaluate a referred, suspected disagreement without having to
reconstruct why it was flagged or manually cross-reference the underlying evidence
themselves. When a genuine unresolved disagreement exists, they receive a structured
representation of the competing positions, the evidence supporting each, and the
assumptions or conditions that distinguish them. When it doesn't — the referral turns out
to reflect a scope, population, timeframe, or definitional difference rather than a real
conflict — they receive that finding instead, rather than a manufactured Ambiguity.

## Design Tensions and Open Questions

1. **Two entry paths, one canonical artifact.** [Resolved: this feature accepts (a) a
   human-initiated referral — the Knowledge Reviewer, while evaluating evidence through
   EA-0008 (Knowledge Review), notices two Candidate Evidence items that may express
   incompatible positions and refers them, without resolving the question themselves; and
   (b) an automatic referral
   from Claim Construction, when synthesis attempts to reconcile competing interpretations
   and cannot. Both converge on one Ambiguity artifact type, which records which path
   produced it.]
2. **Referral vs. detection — where's the boundary?** [Resolved: this feature never
   searches the evidence base or claim set for disagreement on its own. It only evaluates
   and structures a bounded referral it's given. Corpus-wide or pairwise automated
   conflict detection is explicitly deferred to a possible future feature, justified only if
   review throughput becomes a demonstrated bottleneck — not in scope for v1.]
3. **What does a referral actually establish?** [Resolved: only a *suspected* disagreement,
   never a confirmed one. This feature's job is to determine whether the referred items
   represent (a) a genuine unresolved ambiguity, (b) a difference that's actually resolved
   by scope, population, timeframe, or definition — conditionally compatible, not truly in
   conflict — (c) no real conflict at all, or (d) insufficient context to assess yet. **No
   forced reconciliation, in either direction:** the feature must not manufacture false
   consensus just to avoid producing an Ambiguity, and it must not manufacture an Ambiguity
   just because a referral was made, if the evidence doesn't actually support one. A
   reviewer referring two items does not, by itself, create a canonical ambiguity.]
4. **Is Ambiguity mutually exclusive with Claim?** [Resolved: no. A Claim and a linked
   residual Ambiguity can coexist for the same investigation at different granularity —
   e.g. a general claim holds, with a narrower disputed sub-condition recorded alongside
   it rather than either silently dropped or forced to block the general claim.]
5. **What happens after a referral is assessed as (d) "insufficient context"?** [Not
   resolved — genuinely open, unlike #1-4 above. Does the referral stay pending until more
   evidence arrives naturally (e.g. from a later Corpus Construction or Evidence Extraction
   pass), does it require the referring party to actively supply more context before
   re-submission, or does it simply expire unrecorded? Left for Stage 1/2 to decide.]

## Suspected Dependencies

**Direct input dependencies:**
- EA-0004 (Candidate Evidence) — available now, for human-referred pre-claim cases.
- Claim Construction's outputs (Claims, and failed/irreconcilable-synthesis referrals) —
  not yet briefed. This feature requires at least one supported referral input to operate;
  in v1 it can run directly against EA-0004 Candidate Evidence, and once Claim Construction
  exists, its outputs become an *additional* direct input path — this is deliberately not
  phrased as a hard blocking dependency on a feature that doesn't exist yet.

**Invocation sources (distinct from the data itself):**
- The Knowledge Reviewer manually flagging selected Candidate Evidence while evaluating it
  through EA-0008 (Knowledge Review) — meaning EA-0008 isn't only an accept/reject
  checkpoint, it's also a routing point for suspected disagreement. (Another input to
  AJ-001's editorial-consolidation tracking, and now reflected in EA-0008's own brief.)
- Claim Construction (EA-0006) automatically referring a synthesis it cannot reconcile.

**Downstream (hard, now briefed):** EA-0008 (Knowledge Review) consumes constructed
Ambiguities directly — the Knowledge Reviewer's approval of an Ambiguity is owned there, not
by this feature.

**Downstream (soft, not yet briefed):** eventual Publishing views (e.g. a Reality Check's
ambiguity framing) likely consume this feature's output — not confirmed, since Publishing
isn't briefed yet.

## Rough Scope Notes

In scope (rough): evaluating a bounded referral from either entry path; determining whether
the referred items represent genuine ambiguity, conditional compatibility, no real
conflict, or insufficient context to assess; constructing a reviewable representation of
competing positions, their supporting evidence, and the assumptions/conditions that
distinguish them, when genuine ambiguity is found.

Out of scope (rough): claim construction itself; corpus-wide or pairwise automated conflict
detection, or independently searching for disagreements; adjudicating which position is
correct; recommending which side a decision-maker should follow; silently rewriting Claims
or Candidate Evidence to remove a disagreement; forced reconciliation in either direction
(manufacturing consensus, or manufacturing an ambiguity without genuine evidence of one).

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (five listed; #1-4 resolved as principles, #5
      genuinely open)
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
