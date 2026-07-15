# Solution Discovery: EvidenceAtlas

> This document is non-authoritative planning material.
> It does not approve features, architecture, contracts, schemas, events, or implementation.
> If this document conflicts with later approved DBA artifacts, the approved DBA artifacts win.

**Source material:** `backlog/initiate.md` — an exploratory architecture discussion that
reframed the project from "AI system for automated blog article writing" to an
**evidence-first publishing platform for decision-intelligence content**. This document
synthesizes that discussion into the Discovery format. It does not add new decisions beyond
what `initiate.md` already explored, except where explicitly labeled as this review's own
reasoning (risk/recommendation material, not source fact).

Note: `initiate.md` contains **two architecture diagrams from different points in the same
discussion**, and the second silently renames and simplifies the first. See §2 below —
this drift is itself the most important thing this document surfaces.

---

## 1. Domain Problem Framing

- **Core problem:** Publishing content that helps a reader make a decision requires more
  than fluent prose — it requires traceable evidence, explicit handling of disagreement
  between sources, and a way to know when a previously-published claim is stale or has been
  contradicted by new evidence.
- **Primary human actors:**
  - *Editor / reviewer* — approves claims, ambiguities, and recommendations before they
    reach publication; owns epistemological quality, not just prose quality.
  - *Reader / decision-maker* — the consumer of Articles, Reality Checks, Decision Briefs,
    and (future) Topic Pages; needs to know what is known, what is contested, and why.
- **What happens without this system:** ad hoc research-then-write content pipelines where
  claims are not tracked as discrete objects, contradictions are discovered (if at all) only
  when a human happens to re-read old articles, and there is no mechanism to propagate a
  correction across every place a claim was used.
- **Domain-level success:** a corpus of claims and structured ambiguities that is reused
  across multiple published views (article, reality check, decision brief, topic page) from
  a single reviewed source of truth, with known propagation when evidence changes.

## 2. Terminology / Naming Drift

`initiate.md` itself iterated on its own vocabulary between an early diagram and the final
diagram (§9). Neither the discovery process nor this document has reconciled them yet —
Stage 1 should pick one canonical name per concept before writing contracts.

| Diagram 1 (early) | Diagram 2 (final, §9) | Note |
|---|---|---|
| Topic Definition (Topic Registry) | Topic Brief | renamed |
| Research Orchestrator → [Source Discovery, Corpus Quality Analysis] | *(collapsed — no intermediate boxes)* | the author's own later diagram removes these as separate stages entirely, going straight from Topic Brief to Research Corpus |
| Evidence Extraction | Evidence Objects | renamed |
| Claim Construction → [Claim Registry, Ambiguity Registry] | Claim / Ambiguity Construction | registries no longer named separately |
| Editorial Review Gate → [Approved Claims, Approved Ambiguities] | Human Review Gates → Approved Knowledge Registry | pluralized gates; two content registries appear merged into one |
| Publishing Engine | Publishing Views | renamed |

**Why this matters more than a naming nit:** the later diagram collapsing the research-layer
sub-stages away is evidence the author's own thinking already trended toward a *simpler*
design than the elaborate one this document initially preserved. See §8 (Architectural
Risks, P0) and §10 (Explicit Non-Decisions).

## 3. Candidate Feature Topology

Labeled CANDIDATE — none of these are approved Stage 1 intents.

- **CANDIDATE: Topic Registry / Topic Brief** — intake of a topic definition (audience,
  purpose, time horizon, decision type). Upstream of everything else; likely first cluster
  into Stage 1. Canonical name not yet decided — see §2.
- **CANDIDATE (consolidation candidate): Research Orchestration / Source Discovery /
  Corpus Quality Analysis** — assembling a representative research corpus (primary sources,
  academic research, regulators, industry analyses, vendors, deliberately including
  critical/opposing sources) and evaluating it for representativeness. Flagged explicitly as
  "candidate for consolidation" (§2) — the source material's own later diagram collapses
  these three into a single Topic Brief → Research Corpus transition; Stage 1 should
  consciously decide whether to keep three sub-clusters or one.
- **CANDIDATE: `Research Corpus`** — the named output artifact of the research layer
  (explicit in both diagrams and in prose: "Output ni članek. Output je: Research Corpus").
  Previously only implied in this document; now named as its own artifact rather than
  folded into the process cluster that produces it.
- **CANDIDATE: Evidence Extraction / Evidence Objects** — turning raw corpus material into
  discrete `Evidence` objects (excerpt + interpretation), distinct from the source itself.
- **CANDIDATE: Claim Construction** — building `Claim` objects (statement, scope, evidence,
  source excerpt, status) from extracted evidence. Likely the most contract-heavy cluster.
- **CANDIDATE: Ambiguity Construction** — the claimed key differentiator: structuring
  disagreement (conflicting research, competing schools of thought, differing validity
  conditions, open questions) as a first-class object rather than discarding it.
- **CANDIDATE: Claim Registry / Ambiguity Registry (or merged `Approved Knowledge
  Registry`)** — the persisted-store side of Claim/Ambiguity Construction, named separately
  in Diagram 1 and apparently merged in Diagram 2. Whether this is one unified store or two
  is an open naming/design question — see §2.
- **CANDIDATE: Contradiction Resolution Workflow** — the full decision procedure from
  `initiate.md` §4: new evidence → potential contradiction detected → claim status →
  contested → impact analysis → human review → one of {remains active, scope narrowed,
  split, becomes ambiguity, superseded, retired}. Previously only referenced obliquely under
  a risk bullet; promoted here to its own candidate cluster since it's a full workflow, not
  a side effect of Claim Construction.
- **CANDIDATE: Editorial Review Gate / Human Review Gates** — human approval of
  claims/ambiguities before they can feed publishing. Business/governance component, not an
  AI component. Singular vs. plural naming per §2; substance (whether it's one
  undifferentiated gate or the three-tier Gate 1/2/3 structure `initiate.md` proposes later)
  is a P0 open question — see §8.
- **CANDIDATE: Publishing Engine / Publishing Views** — generates multiple views (Article,
  Reality Check, Decision Brief, future Topic Page) from the same approved claims —
  described as the project's main source of scalability.
- **CANDIDATE: Presentation Layer** — Markdown as canonical format, YAML for metadata, MDX
  for enrichment (TL;DR, Reality Check, Evidence Table, Decision Brief), Astro for static
  generation, JSON-LD/sitemap/RSS, and **AI-SEO-friendly HTML** (explicit requirement in
  `initiate.md`, previously dropped from this document).
- **CANDIDATE: Evidence Lifecycle & Governance (control plane)** — identified in
  `initiate.md` as "the last major missing building block": a horizontal layer governing
  status transitions, review policies, freshness monitoring, contradiction handling,
  dependency tracking, change-impact analysis, version history, and publication propagation
  across Source / Evidence / Claim / Ambiguity / Recommendation lifecycles. Its constituent
  objects, previously filed only under Backlog Candidates (an inconsistency — see §8), are
  named here directly as CANDIDATE items:
  - **CANDIDATE: Review Registry** — human decisions, append-only (`initiate.md` §2).
  - **CANDIDATE: Change Event Registry** — event log of significant state changes
    (`initiate.md` §2) — see §8 for how this relates to this project's own DBA event log.
  - **CANDIDATE: Dependency Registry** — claim → dependent-publication mapping
    (`initiate.md` §2) — see §8 for why this is likely a derived index, not a hand-authored
    store.
  - **CANDIDATE: Policy Registry** — declarative rules, e.g. contested-claim publication
    policy (`initiate.md` §2).
- **Deferred clusters (explicitly future, per `initiate.md`):** Entity Registry, Knowledge
  Graph, Semantic Search.

**Independence / shared-vocabulary notes:** Topic Registry → Research → Evidence →
Claim/Ambiguity → Editorial Gate → Publishing forms one largely sequential pipeline.
Evidence Lifecycle & Governance is cross-cutting — it does not sit at one point in the
pipeline but touches Source, Evidence, Claim, Ambiguity, and Recommendation lifecycles
simultaneously, which is why `initiate.md` calls it a "control plane" rather than a stage.

**Needs validation before committing:** whether Editorial Review Gate should be one
undifferentiated gate or the three-tier gate structure `initiate.md` proposes later
(Evidence acceptance / Claim approval / Publication judgement) — see §8 (P0).

## 4. Shared Vocabulary (candidates)

- **Research Corpus** — the representative body of sourced material assembled before
  evidence extraction begins; not an article, an input to it. See §3.
- **Source** — a discovered reference (URL, paper, dataset). Lifecycle candidate:
  `discovered → screened → accepted → monitored → outdated → unavailable → archived`.
- **Evidence** — a concrete excerpt or extraction from a Source, with its own
  interpretation quality independent of the Source's reliability. Lifecycle candidate:
  `extracted → verified → accepted → challenged → superseded → retired`.
- **Claim** — "a verifiable interpretation of evidence," explicitly *not* a truth
  declaration. Lifecycle candidate:
  `draft → in_review → approved → active → contested → superseded → retired`.
  **Unresolved:** `initiate.md` also names **claim split** and **claim merge** as required
  operations (the governance layer must handle "kako se razcepi, kako se združi"), and the
  contradiction-handling flow explicitly includes "claim is split" as an outcome — neither
  operation appears in this lifecycle or in the Event Family Hypotheses below yet. Distinct
  from *what* the states are is *what rule governs* a split/merge — see §8, P1.
- **Ambiguity** — a structured representation of unresolved or contested understanding;
  need not ever reach "resolved" — may instead be merely narrowed. Lifecycle candidate:
  `open → structured → reviewed → published → narrowed → resolved → reopened`.
- **Recommendation** — a normative judgment, held to a stricter gate than a plain claim
  because it prescribes action. Lifecycle candidate:
  `draft → assumption_review → approved → published → invalidated → retired`.
- **risk_level** (`low | medium | high`) — a candidate cross-cutting attribute on claims,
  proposed to modulate review strictness, required independent-source count, review
  interval, and visibility of uncertainty in the published view. **Open question:**
  `initiate.md`'s own examples conflate *stakes/impact* with *volatility/decay rate* under
  this one attribute — see §8, P1, for why these may need to be separate fields.
- **Claim-quality vocabulary (candidate, from `initiate.md`'s Gate 2 checklist):**
  atomicity, falsifiability, anti-triviality, terminological consistency, and
  supporting-vs-opposing evidence — terms multiple future features (claim approval logic,
  reviewer tooling) will need to agree on.

**Vocabulary tension to flag:** `initiate.md` is explicit that *Source* reliability and
*Evidence* interpretation quality are different axes ("a reliable source can still contain
a misinterpreted or irrelevant excerpt") — any later Stage 1 intent should preserve this
distinction rather than collapsing Source and Evidence into one status field.

**See also §2** for the Registry/Gate naming drift not repeated here.

## 5. Review Granularity

A concrete, currently-unanswered question with direct throughput consequences: **what is
the unit of human review?** `initiate.md`'s three-tier gate structure (Gate 1: evidence
acceptance, Gate 2: claim approval, Gate 3: publication judgement) implies review happens
per-object, per-type — but it never says whether review can be batched (e.g., approving a
cluster of related claims in one editorial decision) versus always being one decision per
object instance. This is prior to, and independent of, which object model (Claim-centric,
Bundle-centric, Question-centric — see §9) is eventually chosen, and it is one of the
largest levers on editorial throughput (see §8, P1, "editorial review is a design space").
Not addressed anywhere in `initiate.md` — flagged here as a CANDIDATE open question for
Stage 1.

## 6. Event Family Hypotheses

HYPOTHESIZED only — names and rough shapes, not a schema.

- `SourceDiscovered`, `SourceScreened`, `SourceAccepted`, `SourceOutdated`,
  `SourceUnavailable`, `SourceArchived`
- `EvidenceExtracted`, `EvidenceVerified`, `EvidenceAccepted`, `EvidenceChallenged`,
  `EvidenceSuperseded`
- `ClaimDrafted`, `ClaimSubmittedForReview`, `ClaimApproved`, `ClaimActivated`,
  `ClaimContested`, `ClaimSplit`, `ClaimMerged`, `ClaimSuperseded`, `ClaimRetired` —
  `ClaimSplit`/`ClaimMerged` added per §4's unresolved split/merge operations; naming the
  events doesn't resolve what rule triggers them (see §8, P1).
- `AmbiguityOpened`, `AmbiguityStructured`, `AmbiguityPublished`, `AmbiguityNarrowed`,
  `AmbiguityReopened`
- `RecommendationDrafted`, `RecommendationApproved`, `RecommendationInvalidated`
- `ContradictionDetected` — likely high-signal, cross-cluster event linking a new Source/
  Evidence to an existing active Claim.
- `ImpactAnalysisCompleted` — carries the affected-publications list (articles, reality
  checks, decision briefs, topic pages, JSON-LD summaries) referenced in `initiate.md`'s
  propagation example.
- `PublicationPropagated` — a claim/ambiguity change reflected into downstream published
  views.

**Frequency guess:** Source/Evidence events likely highest-frequency (many sources
screened per topic); Claim/Ambiguity events medium; Recommendation and Contradiction
events lowest-frequency but highest downstream impact.

**Cross-cluster events:** `ContradictionDetected`, `ImpactAnalysisCompleted`, and
`PublicationPropagated` all span Evidence/Claim clusters and the Publishing cluster —
these are candidates that the Evidence Lifecycle & Governance control plane would own
rather than any single pipeline stage.

**Trigger priority (from `initiate.md` §3):** event-based triggers (e.g. a new source
contradicts an active claim, a regulator publishes a new rule, a source becomes
unavailable) are explicitly called out as usually more important than the time-based
`review_after` trigger — worth preserving as a priority principle, not just two
independent trigger types.

## 7. Configuration Hypotheses

`initiate.md` describes policy-as-data more than deployment configuration; the items below
are inferred, not explicit in the source material — flagged accordingly.

```
Config name: review_after_interval
Purpose: default time-based trigger for re-reviewing a claim (e.g. "review_after: +3mo")
Feature(s) likely affected: Evidence Lifecycle & Governance, Claim lifecycle
Default: unset — proposed in initiate.md as per-claim, not global
Required / optional: optional (event-based triggers can substitute or complement)
Secret / non-secret: non-secret
Environment-specific: no
Runtime-changeable: yes (per-claim override expected)
Validation needed: must not conflict with an explicit event-based trigger for same claim
Possible failure mode: stale claim never re-reviewed if both time and event triggers absent
Possible event impact: would emit a review-queue event when interval elapses (not yet named)
```

```
Config name: contested_claim_publication_policy
Purpose: rule governing whether/how a contested claim may remain publicly visible
Feature(s) likely affected: Publishing Engine, Editorial Review Gate
Default: none proposed — initiate.md gives this as an example Policy Registry entry, not a default
Required / optional: required before Publishing Engine can handle contested claims
Secret / non-secret: non-secret
Environment-specific: no
Runtime-changeable: yes (policy registry described as data, not code)
Validation needed: published view must render opposing evidence + contested status together
Possible failure mode: contested claim rendered as uncontested fact if policy not enforced
Possible event impact: ties to ClaimContested / PublicationPropagated
```

**Impact-severity → action policy (candidate, from `initiate.md` §5)** — previously missing
from this document entirely; this is the concrete policy mapping the
`ImpactAnalysisCompleted` event above would need to drive:

| Impact | Action |
|---|---|
| Minor wording change | Automatic suggested correction |
| Scope change | Mandatory editorial review |
| Claim becomes contested | Warning surfaced on all public views |
| Claim retired | Removal or replacement |
| Recommendation loses supporting assumption | Immediate withdrawal |

**Framing questions surfaced, not yet answered:** Is the Policy Registry (`initiate.md`
§2 "Policy Registry") itself a config concern or a Stage-1-behavioral concern (since it
gates what publishes)? This likely needs routing through Stage 1–3 rather than being
treated as deployment configuration — flagged as an open question, not resolved here.

## 8. Architectural Risks

Findings below are grouped by priority, not listed as equally-weighted. P0 items should be
resolved before Stage 1 intents are written for the affected clusters; P1 items are open
architectural questions worth carrying into Stage 1 discussions, not recommendations to
adopt any particular answer.

### P0 — must resolve before Stage 1

1. **Multiple Mutable Sources of Truth (the top risk — reframed from "registry sprawl").**
   Counting every named store across both diagrams gives roughly 9-10 candidate registries
   for a "lean V1" (Topic, Source, Evidence, Claim, Ambiguity, Recommendation, plus
   Review/Change-Event/Dependency/Policy Registry). Raw registry *count* is not the right
   risk metric, though — a registry that is derived (computed from other data) or
   append-only (facts added, never rewritten — exactly how this project's own DBA Decision
   Log already works) is cheap regardless of count. The real danger is the count of
   **independently-mutable authoritative facts**: places where the same fact can be
   authored or edited in more than one location and drift out of sync. **Action:** classify
   every proposed registry as derived/append-only (cheap) vs. independently-mutable
   (expensive), and minimize the expensive category specifically — not the total registry
   count.
   - **Operational cost, not just data-model cost:** every registry that requires a human
     decision adds editorial throughput cost. This should be an explicit design constraint
     ("registry count should be justified by measurable reuse," "every registry requiring
     independent review adds editorial load") — but see P1 below: editorial cost is
     measured by *decisions*, not registries or claims, and it's a lever, not just a cost.
2. **Terminology drift** (§2) — pick one canonical name per concept; explicitly decide
   whether to collapse the research-layer sub-stages per the source's own later diagram.
3. **Governance ownership.** Now resolved in §3 by promoting the four governance registries
   into Candidate Feature Topology directly (they were previously filed only under Backlog
   Candidates while their parent cluster was simultaneously a first-class CANDIDATE and the
   largest named risk — an internal scoping inconsistency). Recorded here so the fix is
   traceable.
4. **Contradiction Resolution Workflow** (§3) — now represented as its own topology entry
   rather than a single risk bullet; the underlying risk (claim-vs-ambiguity boundary
   ambiguity in the "claim becomes ambiguity" outcome) remains open — see P1 below.
5. **Review granularity** (§5) — the unit of human review is undecided and has direct
   throughput consequences; do not let it default silently to per-claim.
6. **Three-tier editorial gate granularity.** `initiate.md` proposes Gate 1/2/3 but also
   says "not every claim needs all three gates." Getting the risk-based gate-skipping rule
   wrong either under-reviews high-stakes recommendations or creates reviewer fatigue on
   low-risk claims — expensive to retrofit once editors have workflow habits built around
   it. Likely where the DBA loop sees the most Stage 1–2 back-and-forth.

### P1 — strong architectural questions (open, not recommendations)

1. **Object lifecycle governance is structural-only, not behavioral.** The architecture
   defines what states Claim/Evidence/etc. can be in, but not what *rule* governs a
   transformation like Claim A splitting into Claim A1 + A2 — editor-triggered,
   evidence-triggered, automatic-with-review, or something else? Applies to
   split/merge/supersession/promotion-to-canonical alike. Distinct from simply having
   `ClaimSplit`/`ClaimMerged` event names (§6) — this is about the governing rule.
2. **Editorial review is a design space, not just a measured bottleneck.** Editorial
   *decision count* (not registry count, not claim count) is the real throughput metric —
   but that count isn't fixed. Example: instead of 20 claims each getting individual
   approval, an AI-assisted clustering pass could group them into 3 bundles for one
   approval each. Worth naming as a lever to architect down, not only a cost to track.
3. **Knowledge volatility class, orthogonal to risk_level.** `risk_level`
   (low/medium/high) as defined conflates *stakes/impact* with *volatility/decay rate* — a
   stable technical fact and a fast-decaying market claim get bucketed by the same field in
   `initiate.md`'s own examples. A stable fact can still be high-stakes; a fast-decaying
   fact can be low-stakes. Worth flagging a candidate second attribute (e.g.
   `knowledge_class: stable | evolving | speculative`) distinct from `risk_level`.
4. **Provenance inheritance across projections.** When the same Claim is cited in an
   Article, a Reality Check, and a Decision Brief, does provenance travel automatically
   from the Claim, or does each published view need to re-establish its own provenance
   trail? Directly relevant to Dependency Registry/propagation (below) but not yet asked.
5. **Claim vs. Ambiguity boundary.** The contradiction-handling flow's "claim becomes
   ambiguity" outcome implies these two object types aren't as cleanly separated as their
   lifecycle diagrams suggest. Not enough evidence yet to recommend a fix — see §9 for why
   a "unify into one type" answer is premature.
6. **Dependency Registry should likely be derived, not hand-maintained.** `claim_id →
   used_by [publications]` can plausibly be computed by scanning which claim_ids each
   published Markdown/MDX file references, rather than authored as an independent registry
   that can drift from actual publication content — the exact class of drift this whole
   architecture exists to prevent for claims/evidence. This is also the clearest concrete
   example of the derived-vs-mutable distinction in risk #1 above.
7. **Policy centralization.** `risk_level` effects and the 3-tier gate system are two
   independently-described governance rule sets that could contradict each other; the
   already-proposed Policy Registry should likely be the single mechanism encoding "which
   gates apply at which risk_level," rather than leaving both as separate prose rules.
8. **Event sourcing — evaluate, don't presume it's more robust.** Deriving object status by
   replaying a Change Event Registry (rather than maintaining independently-mutated status
   fields) would avoid a dual-write bug class, and this project's own DBA Stage 8 (Replay
   Verification) already establishes institutional familiarity with the pattern — but event
   sourcing has real costs too: snapshotting, replay performance, schema evolution/migration
   of historical events, and debugging complexity. Not free, especially for a lean V1. Also
   worth an explicit note that the domain-level Change Event Registry and this project's own
   `events/runtime_events.jsonl` are different layers (domain vs. DBA-meta) and shouldn't be
   conflated.
9. **Propagation correctness.** The Dependency Registry is load-bearing for every
   downstream governance guarantee (impact analysis, propagation, retraction) — see #6
   above for why deriving it is likely the fix, but until resolved, an incomplete or lagging
   mapping degrades every higher-level governance feature silently.
10. **"Missing evidence" as a first-class finding, not a retrieval failure.** If no
    independent studies exist for a claim, that absence may itself be publishable
    information (e.g., in a Reality Check), not merely a gap in the research process. Lower
    priority than the items above — a research-methodology nuance more than a structural
    question.

## 9. Architectural Directions Worth Exploring

Flagged as unevaluated alternatives for Stage 1 discussions to test against a real
intent — **not** recommendations to adopt, and not weighted equally with the sourced
material above.

**Is the architecture object-centric or question-centric?** Everything modeled so far is
Source/Evidence/Claim/Ambiguity/Recommendation as objects with lifecycles. An alternative:
center the architecture on the decision **Question** itself
(`Question → Corpus → Evidence → Competing interpretations → Decision view`), where Claim
is not the stable unit — it's one possible answer, and the Question is what persists
("Should manufacturing SMEs adopt AI coding agents?" is stable; claims about it are not).
**Sharpened version:** make "competing interpretations" explicit as competing
**Hypotheses** (H1/H2/H3), with evidence supporting/weakening each, and the Decision Brief
reading as "given current evidence, H2 is best supported under assumptions X." This is not
a fourth independent architecture — it's the Question-centric direction made concrete.

**Evidence Bundle — an attractive but unproven alternative to Claim as the reusable
unit.** Since Claims are explicitly *interpretations* (Core Principle #2, §10), one step
removed from raw material, a candidate structure is
`Source → Evidence Object → Evidence Bundle → Claim → Ambiguity/Recommendation → Views`,
where Evidence Bundle (not Claim) is the stable reusable object and Claims become
projections of it — re-derivable if editorial policy changes, without redoing research.
**Caveat:** Evidence Bundle inherits the same unresolved problem Claims have — who defines
a bundle's boundaries? Do two editors building a bundle over the same corpus converge on
the same bundle? Can bundles overlap? Without answering that, this isn't a solved
improvement over Claim, it's the same atomization problem one layer down.

**Corpus reuse across topics.** The current model treats each Topic as spinning up its own
Research → Evidence pipeline. But topics like "AI agents," "AI governance," "Enterprise
AI," and "Automation ROI" plausibly draw on heavily overlapping sources. A
`Corpus → Evidence Library → topic-specific reasoning` structure (shared evidence layer,
topic-specific interpretation on top) could be a large efficiency gain versus fully-isolated
per-topic research. Entirely unaddressed in the source material.

**Two complementary framings (not competing — different layers of the same system):**
- *Knowledge Compiler* (implementation-mechanics lens): Sources as input; Evidence/Claims/
  Ambiguities as an intermediate representation; Review/Governance/Freshness as
  optimization/verification passes; Article/Decision Brief/Reality Check/Topic Page as
  codegen targets from the same IR. Suggests clearer stage boundaries, immutable
  intermediate artifacts, deterministic builds, incremental recompilation when evidence
  changes, impact analysis as dependency analysis, publication as code generation — and
  lines up with the DBA/Codeos methodology this project already runs on.
- *Evidence-Synthesis Pipeline* (domain/epistemics lens): the same architecture also reads
  like a systematic-review process — research protocol → evidence acquisition →
  interpretation → peer review → publication → continuous revision — surfacing
  methodological-rigor concerns a pure build-system framing wouldn't naturally raise.

Neither framing corrects the other; they describe mechanics vs. epistemics respectively.
Worth naming both, not picking one.

## 10. Core Principles (from `initiate.md`)

Previously diffused across Domain Framing and Vocabulary; given first-class treatment here
since they read as architectural invariants later Stage 1 intents should be checked against:

1. **Evidence before prose** — evidence exists before text is written about it.
2. **Claims are interpretations** — a claim is not truth, it is a verifiable interpretation
   of evidence.
3. **Preserve uncertainty** — uncertainty is structured, not hidden.
4. **Reuse reviewed knowledge** — a reviewed claim is used many times; articles are not
   re-verified from scratch each time.
5. **Decision support, not truth declaration** — the system helps a reader understand what
   is known, what is unknown, why experts disagree, and which assumptions drive different
   conclusions; it does not declare truth.

## 11. Explicit Non-Decisions

- **Out of scope for v1** (per `initiate.md` §8 "Minimalna implementacija za V1"): no
  workflow engine — file-based data (`/data/sources/*.yaml`, `/data/evidence/*.yaml`,
  `/data/claims/*.yaml`, `/data/ambiguities/*.yaml`, `/data/reviews/*.yaml`,
  `/data/events/*.yaml`, `/data/policies/*.yaml`) with deterministic validations is
  explicitly sufficient; framed as a CLI/build-time pipeline, no database required for v1.
- **Explicitly deferred entirely:** Entity Registry, Knowledge Graph, Semantic Search
  (listed under "Future" in the architecture diagram, not v1 scope).
- **Whether to keep three separate research-layer clusters (Research Orchestration /
  Source Discovery / Corpus Quality Analysis) or collapse them per the source material's
  own later diagram** (§2) — an explicit decision Stage 1 must make, not assume.
- **Risk of scope creep if Stage 1 intents are written too broadly:** treating this as a
  general-purpose CMS or a generic fact-checking tool rather than a decision-support
  publishing system scoped to evidence/claim/ambiguity handling for a specific topic
  intake flow.

## 12. Next Step: Shift from Document Review to Empirical Validation

Further value is unlikely to come from another round of discovery-doc refinement — the
remaining open questions (§8 P1, §9) are empirical, not conceptual:

1. What is the smallest useful unit of review? (source / evidence / claim / bundle /
   question / article / topic — see §5)
2. Can research/evidence be reused across topics without losing topical relevance? (§9)
3. What is the actual editorial decision count per published topic, in practice — and can
   it be reduced by restructuring the review workflow rather than just measured? (§8, P1.2)
4. Is the architecture fundamentally Claim-centric (current design), or
   Question/Hypothesis-centric (§9)?

**Concrete proposal:** build two competing micro-prototypes against the same test topic
(e.g. "Should manufacturing SMEs adopt AI coding agents?") — (1) Claim-centric, the current
design, and (2) Question/Hypothesis-centric — and compare them on: editorial decisions
required, review time, traceability, ease of updating when evidence changes, and quality of
the resulting Decision Brief. That comparison is likely to resolve more architectural
uncertainty than further document analysis.

This does not replace settling the P0 items in §8 first — the prototypes still need the
terminology (§2) and governance-ownership (§3/§8) questions resolved, since those affect
what actually gets built.

## Backlog Candidates (out of scope for this Discovery session)

- The V1 minimal deterministic validation list (`initiate.md` §8, e.g. "active claim must
  have an approved review," "retired claim must not feed new content") reads as
  behavioral-contract material (Stage 2 Given/When/Then candidates) rather than discovery
  material — noting it here so it isn't lost, but not drafting contracts in this session.
