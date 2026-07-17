# Feature Brief: EA-0001 — Research Brief

**Slug**: research_brief
**Type**: F-type
**Refines**: n/a
**Tier**: 0 — Foundational (first domain feature; nothing upstream to depend on)
**Status**: BRIEF-DRAFT

---

## Problem / Need

Decision-makers today rely on fragmented, inconsistent, often hype-driven information
spread across many sources. Existing AI tools can summarize that information, but they
don't ensure the scope of an investigation is explicit, that opposing viewpoints are
intentionally included, that the question being investigated is actually well-defined, or
that assumptions and exclusions are recorded anywhere. As a result, every research effort
effectively starts from scratch, even when a similar question was investigated before, and
nobody downstream can reconstruct why an investigation took the path it did.

## Primary Actor

The Editor / Research Lead — the person who decides which question deserves investigation,
why it's strategically relevant, who the intended audience is, and what decision the
research is meant to support.

## Core Outcome (informal)

The Editor establishes a research contract — captured as a single reviewable artifact —
that names a decision problem, not a topic, and hands it to the research pipeline as the
explicit terms of investigation: the same question, the same assumptions, the same
audience, the same boundaries, every time. Within that contract, *why the investigation
exists* (Research Intent) is deliberately kept separate from *what is being decided*
(Decision Question) — collapsing the two tends to quietly smuggle a preferred answer into
the question itself. Success is not "the AI has enough information," and it isn't
word-for-word identical output either — it's that any compliant pipeline handed the same
brief investigates the same question, stays within the same scope, and preserves the same
assumptions, even if the resulting prose differs.

## Design Tensions and Open Questions

1. Where does human intent end and machine reasoning begin? [Tentative: the human owns the
   Decision Question, Research Intent, Decision Context, Audience, Scope, Exclusions,
   Success Criteria, and Constraints. Deriving Research Questions, a research plan, a search
   strategy, source discovery, corpus construction, and gap analysis all belong to a later
   feature — if this feature starts producing any of those, it has quietly become "Research
   Planning," a different capability.]
2. Is "Research Intent" (why the investigation exists, what the output should emphasize —
   e.g. evidence and uncertainty over a specific product recommendation) genuinely distinct
   from "Decision Question" (what is being decided), or could the two be merged?
   [Tentative: keep them separate — see Core Outcome above.]
3. Should a Research Brief always represent a single decision problem, or can one brief
   intentionally encompass multiple related decisions (e.g. "adopt AI agents OR RPA," or
   "compare five options")? [No tentative answer yet — this affects what "complete" means
   for the artifact and will likely become an acceptance criterion in Stage 1/2.]
4. How should a topic-only input (e.g. "AI Agents") or a decision question missing an
   actor/domain/timeframe/decision (e.g. "Should we use AI?") be handled? [Tentative: reject
   with an explanation of what's missing, rather than silently inferring or rewriting it for
   the human.]
5. Can this artifact be edited after research has started on it? [Tentative: no — it
   progresses through something like Draft → Approved → Research Started → Locked; once
   research has started, further change happens only as an explicit new revision, never an
   in-place edit, so it stays possible to know which version produced which corpus. Needs
   Stage 1/2 to confirm the actual states and transition triggers.]
6. Should this feature define a structured vocabulary (enums, taxonomy) for fields like
   audience or scope now, or leave them as free text until real usage reveals the patterns?
   [Tentative: free text only for v1 — inventing an ontology now is likely to be wrong and
   get replaced once a couple dozen real briefs exist.]
7. Should this feature avoid referencing any vocabulary from downstream stages entirely
   (claims, ambiguity, evidence, corpus, recommendations, publishing) so the dependency
   direction stays one-way? [Tentative: yes — this artifact should be describable and
   buildable without knowing any of those concepts exist yet.]

## Suspected Dependencies

None suspected upstream — this is intentionally the first operational domain artifact in
the system. It depends only on general project infrastructure (however artifacts end up
being stored), not on any other domain feature.

Downstream, a not-yet-defined research-planning/question-derivation capability, and
whatever downstream evidence-acquisition and interpretation capabilities eventually exist,
seem likely to need the Decision Question and/or Research Intent as direct input — named
generically here since their eventual shapes and names aren't yet settled. These are
beliefs about capabilities that don't exist yet, not architectural decisions — Stage 1 for
each of those features will verify.

One dependency this feature should explicitly **not** have: it should never need to know
about any downstream concept (claims, evidence, corpus, recommendations, publishing) to be
fully specified. If drafting Stage 1 for this feature ends up requiring one of those
concepts, that's a sign the boundary above has slipped.

## Rough Scope Notes

In scope (rough): capturing a Decision Question, Research Intent, Decision Context,
Audience, Scope, Out-of-Scope items, Success Criteria, and Constraints as one reviewable
artifact; rejecting a submission that's a bare topic or missing key elements of a decision
question, with an explanation of what's missing; some kind of lifecycle that prevents
silent in-place edits once research has begun.

Out of scope (rough): deriving Research Questions or a research plan; search strategy or
source discovery; rewriting or improving the human's decision question with AI (validation
that it's well-formed is plausible, rewriting it is not); deduplication or similarity search
against other briefs; multi-person approval routing (single editor, single review is enough
for v1); any ontology/taxonomy for fields like audience or industry; and any field that
would let the human record an expected answer, preferred outcome, or desired recommendation
— capturing that would undermine the point of an evidence-first pipeline before it starts.

**Note (architectural assumption, not a guarantee):** this artifact is currently expected to
be the only human-authored domain artifact in the initial vertical slice, with everything
else in the pipeline derived from it. This is a tentative design intent, not a fixed
invariant — if later work (e.g. the vertical-slice comparison from
`docs/solution-discovery-evidenceatlas.md`) shows editors need to author something else
independently, this assumption should be revisited rather than treated as binding.

## Readiness Check

- [x] The problem statement explains WHY, not HOW
- [x] The primary actor is a human role, not "the system"
- [x] The core outcome is stated from the actor's perspective
- [x] At least one open question is listed (seven listed)
- [x] Suspected dependencies are named (even if marked uncertain)
- [x] No actor+outcome DBA form appears anywhere in this brief
- [x] No stable guarantees or DBA scope boundaries appear in this brief (the one
      architectural note is explicitly labeled as a non-binding assumption)
- [x] The feature can be described without mentioning implementation technology
- [x] (R-type only) — n/a, this is F-type

**Brief status**: READY FOR STAGE 1

---

<!-- METADATA -->
brief_created: 2026-07-16
brief_last_updated: 2026-07-17
stage1_started:
