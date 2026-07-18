# Feature Brief: EA-0010 — Policy Registry

**Slug**: policy_registry
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational, but the first member of the "Authority Layer" (per Architecture
Journal AJ-004) rather than a pipeline stage — consulted across investigations, not scoped
to a single one.
**Status**: BRIEF-DRAFT

---

## Problem / Need

Without a single authoritative place to declare rules like "is this checkpoint blocking or
advisory," "what review sampling strategy applies," or "what framing is required before a
contested claim publishes," each feature that needs such a rule would either hardcode it
(making the rule invisible and hard to change) or duplicate near-identical prose across
briefs — already starting to happen, since EA-0007, EA-0008, and EA-0009 each independently
say "consult the Policy Registry" for a different concern. Without one, an editorial policy
change would require touching multiple features instead of one shared, declared rule.

## Primary Actor

The **Editor / Research Lead** — the same role used throughout, not a new "Policy
Administrator." Per Architecture Journal AJ-004, policy authorship here is infrequent and
editorial in nature (these are editorial governance decisions, like review strictness and
publication framing, not infrastructure administration), so introducing a dedicated role
now would be premature specialization.

## Core Outcome (informal)

The Editor can declare and adjust a normative rule governing a specific decision point —
e.g. whether Investigation Review is blocking, what review granularity applies to evidence
acceptance, what framing a contested claim requires before publishing — in one place, and
have every feature that consults that decision point apply the current rule consistently,
without needing to change how any of those features are themselves built.

## Design Tensions and Open Questions

1. **Is this an Authority Service, not a transformation or governance feature?**
   [Resolved, per AJ-004: yes. Its actor question is "who authors the rule," not "who
   benefits from a transformation or approves an artifact." It's distinguished from
   investigation-scoped artifacts (Research Brief, Research Plan) by lifecycle — a policy
   applies across many investigations, not one.]
2. **Is this one registry, or several, given the rules span very different domains** (review
   blocking, publication framing, risk-level effects, sampling)? [Resolved: one registry,
   unified not by domain but by a single common shape — every entry is a rule that governs
   one decision point. That's a coherent responsibility even though the domains differ, the
   same way "Evidence" stays one coherent type despite coming from very different source
   domains.]
3. **Do policy changes need their own governance/review checkpoint?** [Resolved: no
   dedicated review-feature checkpoint — that would create an infinite regress (Policy →
   Policy Review → Policy-Policy Review) and conflates operational configuration with
   epistemic governance. Policy changes are versioned and auditable (who changed what,
   when), but sit outside the Investigation/Knowledge/Publication Review classes from
   AJ-003, not as a fourth phase.]
4. **Can policy eliminate a governance checkpoint's existence, or only modulate how it
   happens?** [Not resolved — and not the same question as #3. A policy that sets a
   checkpoint to advisory, or adjusts its sampling rate, modulates *how* it happens. A
   policy that could disable Investigation, Knowledge, or Publication Review outright for
   some content class would eliminate the checkpoint's *existence*. Given how much this
   project's premise depends on those three governance classes actually running, there's
   likely a floor here: policy should configure how a checkpoint behaves, not whether it
   exists for content that would otherwise require it. Needs Stage 1/2 to confirm this
   boundary explicitly — without it, Policy Registry could become a way to quietly defeat
   the governance architecture already established.]
5. **What happens when no policy exists yet for a decision point a feature needs?** [Not
   resolved — does the consuming feature fall back to a hardcoded conservative default
   (e.g., blocking, full review), or fail/escalate instead? Left open.]

## Suspected Dependencies

Upstream: none — this is authored directly by the Editor, not derived from any other
feature's output.

Downstream (hard, existing): EA-0007 (Investigation Review), EA-0008 (Knowledge Review),
and EA-0009 (Publication Review) each already recorded a forward-reference belief that they
consult this registry — for blocking-vs-advisory rules, review granularity/sampling
strategy, and publication framing requirements respectively. This brief confirms the
registry exists to satisfy those beliefs.

Downstream (soft, forward): the not-yet-briefed Dependency Registry, Review Registry, and
Change Event Registry may also consult or sit alongside this one as fellow Authority-Layer
members — not yet confirmed.

## Rough Scope Notes

In scope (rough): declaring and storing rules that govern specific decision points across
Investigation/Knowledge/Publication Review and any other feature that needs one; versioning
and audit history of policy changes; providing the currently-applicable rule when a feature
consults it.

Out of scope (rough): making the review or approval decisions itself (each governance
feature's own job — this only supplies the rule they apply); a dedicated Policy
Administrator role; a formal governance/review checkpoint for policy changes themselves;
any hardcoded domain-specific taxonomy of rule types beyond "a rule governs a decision
point."

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (five listed; #1-3 resolved as principles, #4-5
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
brief_created: 2026-07-18
brief_last_updated: 2026-07-18
stage1_started:
