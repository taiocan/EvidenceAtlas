# Feature Brief: EA-0006 — Claim Construction

**Slug**: claim_construction
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational (depends on EA-0008's Accepted Evidence output — see Suspected
Dependencies)
**Status**: BRIEF-DRAFT

---

## Problem / Need

Accepted evidence, even once verified as faithful to its sources, is still just a
collection of individually-grounded excerpts and interpretations — nobody has yet
synthesized what defensible proposition, if any, that evidence supports for a given
Research Question. Without this feature, every downstream use of the evidence base
(publishing, decision-brief generation) would need to re-derive that synthesis itself,
inconsistently and without a reviewable intermediate record of what was concluded and why.

## Primary Actor

**Correction (2026-07-18, per Architecture Journal AJ-003):** the actor for this feature is
the **Knowledge Reviewer** — the same unified role used for EA-0004 and EA-0005 (this
section previously named a standalone future "Claim Reviewer"; that name is retired). The
question the Knowledge Reviewer asks here is specifically whether a proposed Candidate
Claim is sufficiently supported, bounded, and decision-relevant to enter the accepted claim
base — a different question from evidence acceptance or ambiguity approval, but asked by
the same role. Today, without this feature, that person would have no synthesized
proposition to evaluate at all — they'd have to read raw accepted evidence and construct an
interpretation themselves before they could even begin reviewing one.

## Core Outcome (informal)

The Knowledge Reviewer can evaluate a proposed, defensible proposition synthesized from
accepted evidence — with its supporting and limiting evidence, scope, qualifiers, and
synthesis rationale already attached — rather than having to synthesize it themselves
before they can review it. When the accepted evidence for a Research Question can't be
responsibly reconciled into any claim, they instead see that outcome recorded honestly
(and, where relevant, referred to Ambiguity Construction) rather than a forced or
overreaching proposition.

## Design Tensions and Open Questions

1. **Construction vs. approval — same split as Evidence Extraction / Knowledge Review.**
   [Resolved: this feature only produces Candidate Claims; it never approves, rejects, or
   decides a claim is authoritative, and never silently revises a claim after a reviewer has
   looked at it. EA-0008 (Knowledge Review) owns that decision. The independent-actor-value
   test gives the same answer as before — a Candidate Claim has clear review value on its
   own, and "accepted claim" is a materially different state produced by a distinct human
   judgment.]
2. **Does this feature consume raw Candidate Evidence or EA-0008-accepted Evidence?**
   [Resolved: Accepted Evidence only. Operating on unreviewed Candidate Evidence would let
   a hallucinated or misinterpreted candidate influence synthesis before the human
   acceptance step meant to catch exactly that. This corrects EA-0004's brief, which
   previously said Claim Construction consumes Candidate Evidence directly — see the
   correction note added there.]
3. **Does one Research Question resolve to exactly one Claim?** [Resolved: no — a Research
   Question can produce zero, one, or multiple Claims, addressing different dimensions
   (magnitude, mechanism, boundary conditions, risks, evidence limitations) that coexist
   and qualify each other rather than conflict. Multiple claims on the same Research
   Question are not automatically an ambiguity — they become one only when the
   interpretations genuinely compete and that competing relationship itself needs
   structuring (Ambiguity Construction's job, not this feature's). Legitimate outcomes for
   a Research Question also include: no accepted evidence exists yet, the evidence is
   insufficient to synthesize anything defensible, or the result is an Ambiguity referral
   with no accompanying Claim at all.]
4. **Does canonical ownership of "Evidence Category" finally land here?** [Resolved: no,
   deferred again — this would conflate what a piece of evidence *is* with what can be
   *synthesized from it*. Instead, this feature originates a narrower, more load-bearing
   vocabulary: the **Claim-Evidence relationship** (supports, opposes, qualifies, limits,
   contextualizes, insufficient-to-determine) — how accepted Evidence bears on a specific
   Candidate Claim. Evidence-intrinsic characteristics (empirical study, official
   statistics, regulation, vendor case study, etc.) belong with the Evidence model or
   EA-0008's acceptance layer instead, whenever that gets defined.]
5. **Relationship to existing Ambiguities.** [Not resolved — left open rather than forced.
   Could a later Claim Construction run (e.g. against updated evidence) reference an
   already-constructed Ambiguity to properly scope or qualify a new claim around a known
   disputed sub-condition? Plausible, but not required for this feature to function, and
   deliberately left as a later dependency question rather than decided now.]

## Suspected Dependencies

Upstream (hard): EA-0008 (Knowledge Review)'s **Accepted Evidence** output — not Candidate
Evidence directly (see resolution #2 above). This feature also consumes Research Questions
and their upstream traceability context (from EA-0002's Research Plan, carried through
EA-0008's acceptance step).

Downstream (hard): EA-0008 (Knowledge Review) consumes Candidate Claims directly, and its
Knowledge Reviewer owns accept/reject/return-for-revision on them.

Downstream (hard, existing): EA-0005 (Ambiguity Construction) consumes referrals from this
feature when synthesis can't reconcile competing interpretations for a Research Question —
already established when EA-0005 was briefed.

Downstream (soft, open): whether a later Claim Construction run should be able to reference
an existing Ambiguity when scoping a new claim (see Design Tension #5) — not decided.

## Rough Scope Notes

In scope (rough): synthesizing zero or more Candidate Claims per Research Question from
Accepted Evidence (produced via EA-0008); attaching supporting and limiting evidence to
each; recording scope, qualifiers, and synthesis rationale; originating the Claim-Evidence
relationship vocabulary; referring irreconcilable synthesis results to Ambiguity
Construction.

Out of scope (rough): claim approval or rejection, and evidence acceptance (both EA-0008's
job); the canonical Evidence Category taxonomy (deferred, likely belongs with the Evidence
model or EA-0008); adjudicating or resolving Ambiguities; forcing exactly one claim per
Research Question, or forcing any claim to be produced when the evidence doesn't support
one.

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (five listed)
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
