# Solution Discovery: FactForge

> This document is non-authoritative planning material.
> It does not approve features, architecture, contracts, schemas, events, or implementation.
> If this document conflicts with later approved DBA artifacts, the approved DBA artifacts win.

**Source material:** `backlog/initiate.md` — an exploratory architecture discussion that
reframed the project from "AI system for automated blog article writing" to an
**evidence-first publishing platform for decision-intelligence content**. This document
synthesizes that discussion into the Discovery format. It does not add new decisions beyond
what `initiate.md` already explored.

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

## 2. Candidate Feature Topology

Labeled CANDIDATE — none of these are approved Stage 1 intents.

- **CANDIDATE: Topic Registry** — intake of a topic definition (audience, purpose, time
  horizon, decision type). Upstream of everything else; likely first cluster into Stage 1.
- **CANDIDATE: Research Orchestration / Source Discovery** — assembling a representative
  research corpus (primary sources, academic research, regulators, industry analyses,
  vendors, and deliberately including critical/opposing sources).
- **CANDIDATE: Corpus Quality Analysis** — evaluating the research corpus for
  representativeness before evidence extraction begins.
- **CANDIDATE: Evidence Extraction** — turning raw corpus material into discrete `Evidence`
  objects (excerpt + interpretation), distinct from the source itself.
- **CANDIDATE: Claim Construction** — building `Claim` objects (statement, scope, evidence,
  source excerpt, status) from extracted evidence. Likely the most contract-heavy cluster.
- **CANDIDATE: Ambiguity Construction** — the claimed key differentiator: structuring
  disagreement (conflicting research, competing schools of thought, differing validity
  conditions, open questions) as a first-class object rather than discarding it.
- **CANDIDATE: Editorial Review Gate** — human approval of claims/ambiguities before they
  can feed publishing. Business/governance component, not an AI component.
- **CANDIDATE: Publishing Engine** — generates multiple views (Article, Reality Check,
  Decision Brief, future Topic Page) from the same approved claims — described as the
  project's main source of scalability.
- **CANDIDATE: Presentation Layer** — Markdown as canonical format, YAML for metadata,
  MDX for enrichment (TL;DR, Reality Check, Evidence Table, Decision Brief), Astro for
  static generation, JSON-LD/sitemap/RSS.
- **CANDIDATE: Evidence Lifecycle & Governance (control plane)** — identified in
  `initiate.md` as "the last major missing building block": a horizontal layer governing
  status transitions, review policies, freshness monitoring, contradiction handling,
  dependency tracking, change-impact analysis, version history, and publication
  propagation across Source / Evidence / Claim / Ambiguity / Recommendation lifecycles.
- **Deferred clusters (explicitly future, per `initiate.md`):** Entity Registry, Knowledge
  Graph, Semantic Search.

**Independence / shared-vocabulary notes:** Topic Registry → Research → Evidence →
Claim/Ambiguity → Editorial Gate → Publishing forms one largely sequential pipeline.
Evidence Lifecycle & Governance is cross-cutting — it does not sit at one point in the
pipeline but touches Source, Evidence, Claim, Ambiguity, and Recommendation lifecycles
simultaneously, which is why `initiate.md` calls it a "control plane" rather than a stage.

**Needs validation before committing:** whether Editorial Review Gate should be one
undifferentiated gate or the three-tier gate structure `initiate.md` proposes later
(Evidence acceptance / Claim approval / Publication judgement) — see Architectural Risks.

## 3. Shared Vocabulary (candidates)

- **Source** — a discovered reference (URL, paper, dataset). Lifecycle candidate:
  `discovered → screened → accepted → monitored → outdated → unavailable → archived`.
- **Evidence** — a concrete excerpt or extraction from a Source, with its own
  interpretation quality independent of the Source's reliability. Lifecycle candidate:
  `extracted → verified → accepted → challenged → superseded → retired`.
- **Claim** — "a verifiable interpretation of evidence," explicitly *not* a truth
  declaration. Lifecycle candidate:
  `draft → in_review → approved → active → contested → superseded → retired`.
- **Ambiguity** — a structured representation of unresolved or contested understanding;
  need not ever reach "resolved" — may instead be merely narrowed. Lifecycle candidate:
  `open → structured → reviewed → published → narrowed → resolved → reopened`.
- **Recommendation** — a normative judgment, held to a stricter gate than a plain claim
  because it prescribes action. Lifecycle candidate:
  `draft → assumption_review → approved → published → invalidated → retired`.
- **risk_level** (`low | medium | high`) — a candidate cross-cutting attribute on claims,
  proposed to modulate review strictness, required independent-source count, and review
  interval.

**Vocabulary tension to flag:** `initiate.md` is explicit that *Source* reliability and
*Evidence* interpretation quality are different axes ("a reliable source can still contain
a misinterpreted or irrelevant excerpt") — any later Stage 1 intent should preserve this
distinction rather than collapsing Source and Evidence into one status field.

## 4. Event Family Hypotheses

HYPOTHESIZED only — names and rough shapes, not a schema.

- `SourceDiscovered`, `SourceScreened`, `SourceAccepted`, `SourceOutdated`,
  `SourceUnavailable`, `SourceArchived`
- `EvidenceExtracted`, `EvidenceVerified`, `EvidenceAccepted`, `EvidenceChallenged`,
  `EvidenceSuperseded`
- `ClaimDrafted`, `ClaimSubmittedForReview`, `ClaimApproved`, `ClaimActivated`,
  `ClaimContested`, `ClaimSuperseded`, `ClaimRetired`
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

## 5. Configuration Hypotheses

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

**Framing questions surfaced, not yet answered:** Is the Policy Registry (`initiate.md`
§2 "Policy Registry") itself a config concern or a Stage-1-behavioral concern (since it
gates what publishes)? This likely needs routing through Stage 1–3 rather than being
treated as deployment configuration — flagged as an open question, not resolved here.

## 6. Architectural Risks

- **Claim vs. Ambiguity boundary.** `initiate.md`'s contradiction-handling flow shows a
  contested claim can resolve into "claim becomes ambiguity" — the boundary between these
  two object types is a design decision that would be expensive to change after claims and
  ambiguities have separate storage/lifecycle implementations.
- **Three-tier editorial gate granularity.** `initiate.md` proposes Gate 1 (Evidence
  acceptance) / Gate 2 (Claim approval) / Gate 3 (Publication judgement), but also says
  "not every claim needs all three gates." Getting the risk-based gate-skipping rule wrong
  either under-reviews high-stakes recommendations or creates reviewer fatigue on
  low-risk claims — expensive to retrofit once editors have workflow habits built around it.
  This is likely where the DBA loop sees the most back-and-forth (Stage 1–2 revisions).
- **Propagation correctness.** The Dependency Registry (claim → dependent publications) is
  load-bearing for every downstream governance guarantee (impact analysis, propagation,
  retraction). If this mapping is incomplete or lags actual publication state, every
  higher-level governance feature silently degrades without an obvious symptom.
  High-uncertainty, high-cost-if-wrong.
  external dependencies to verify: none named explicitly in `initiate.md` (no specific
  external API/vendor called out yet) — flagged as an open question for Stage 1 intents
  that touch Source Discovery.
- **Governance layer sequencing risk.** `initiate.md` itself frames Evidence Lifecycle &
  Governance as the piece that turns the architecture from "a collection of good ideas"
  into "a coherent system" — meaning building pipeline features (Evidence/Claim/Publishing)
  without early agreement on lifecycle state machines risks rework once governance is
  formalized. This is the single largest sequencing risk surfaced in the source material.

## 7. Explicit Non-Decisions

- **Out of scope for v1** (per `initiate.md` §8 "Minimalna implementacija za V1"): no
  workflow engine — file-based data (`/data/sources/*.yaml`, `/data/evidence/*.yaml`,
  `/data/claims/*.yaml`, `/data/ambiguities/*.yaml`, `/data/reviews/*.yaml`,
  `/data/events/*.yaml`, `/data/policies/*.yaml`) with deterministic validations is
  explicitly sufficient; framed as a CLI/build-time pipeline, no database required for v1.
- **Explicitly deferred entirely:** Entity Registry, Knowledge Graph, Semantic Search
  (listed under "Future" in the architecture diagram, not v1 scope).
- **Risk of scope creep if Stage 1 intents are written too broadly:** treating this as a
  general-purpose CMS or a generic fact-checking tool rather than a decision-support
  publishing system scoped to evidence/claim/ambiguity handling for a specific topic
  intake flow.

## Backlog Candidates (out of scope for this Discovery session)

- The full Review Registry / Change Event Registry / Dependency Registry / Policy
  Registry YAML shapes in `initiate.md` §2 are close to schema-ready — worth flagging as
  strong starting material for a future Stage 3 event schema, but that drafting belongs
  in Stage 1–3 of a specific feature, not in this Discovery document.
- The V1 minimal deterministic validation list (`initiate.md` §8, e.g. "active claim must
  have an approved review," "retired claim must not feed new content") reads as
  behavioral-contract material (Stage 2 Given/When/Then candidates) rather than discovery
  material — noting it here so it isn't lost, but not drafting contracts in this session.
