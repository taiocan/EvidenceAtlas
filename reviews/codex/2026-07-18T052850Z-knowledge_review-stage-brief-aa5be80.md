---
review_id: REV__knowledge_review__brief__R1
findings: []
unparsed_findings_count: 0
reviewed:
  feature: knowledge_review
  stage: brief
  branch: main
  base_commit: (no base pin)
  review_commit: aa5be800de44b6dd7ac02a88eddb163baf5d85ff
  artifacts:
    - path: backlog/EA-0008-knowledge_review.md
      sha256: fcf0d671aca1237a3430a9be76020959719c12e263f1f37078832a750eaa1efb
      visibility: shown
    - path: backlog/EA-0004-evidence_extraction.md
      sha256: 42739674a4d4ca824c8d90b2121736e82f9724687eb138a1574a5b71c03b658a
      visibility: shown
    - path: backlog/EA-0005-ambiguity_construction.md
      sha256: a4134a75cdf2bdaf1eaad55943eb2ab0def9c96cac5da9cd595dfe105f2cb85a
      visibility: shown
    - path: backlog/EA-0006-claim_construction.md
      sha256: 47c1199b1410ae2e550ba742141e6c717cddb3bacb92d95db946cf1c9339d080
      visibility: shown
  diff_hash: e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
  coverage_state: FULL_COVERAGE
  workspace_dirty: true
  redaction_count: 0
  secret_redaction: false
  excluded_paths: []
  reviewed_packet: packets/20260718T052850Z-knowledge_review-stage-brief-aa5be80.packet.txt
  reviewed_packet_sha256: a9c281494b7da3cb8831137653e1294ec4be6fe6e51c862e56ca391d62b017e2
  reviewer: "codex (session 019f73b1-d534-7052-8a04-557f4b5354ed)"
  codex_concern: NO OBJECTION
  effective_concern: NO OBJECTION
  evidence: A
  reasoning_effort: high
  reconnect_count: 0
  elapsed_ms: 68683
---

**Acceptance Criteria**

1. Problem clearly stated: satisfied. EA-0008 states the gap: no owner exists for checking whether evidence, claims, and ambiguities become trustworthy knowledge before entering the trusted base ([backlog/EA-0008-knowledge_review.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:14), [line 20](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:20)).

2. Scope explicitly bounded: satisfied. In-scope review activities are listed, and exclusions are explicit: no candidate production, no investigation/publication approval, no Policy Registry definition ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:84), [line 91](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:91)).

3. No implementation detail: satisfied. The brief describes roles, candidate artifacts, outcomes, dependencies, and policy consultation, but no implementation technology; the readiness check also asserts this ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:105)).

4. Ready to become Stage 1 Intent: satisfied. It has problem, actor, outcome, open questions, dependencies, informal scope, and marks “READY FOR STAGE 1” ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:95), [line 108](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:108)).

5. Value/risk/guardrail present: satisfied. Value/risk: prevents possibly hallucinated material from silently reaching publication ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:14)). Guardrails: review owns trust decisions but not producing candidates, investigation approval, publication approval, or the Policy Registry ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:86), [line 91](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:91)).

**Claim Support**

Strong claims are sufficiently supported for this stage. The unified “Knowledge Reviewer” role is backed by matching corrections in EA-0004, EA-0005, and EA-0006 ([EA-0004](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:23), [EA-0005](/home/rimo/projects/EvidenceAtlas/backlog/EA-0005-ambiguity_construction.md:23), [EA-0006](/home/rimo/projects/EvidenceAtlas/backlog/EA-0006-claim_construction.md:23)). The claim that EA-0008 consumes Candidate Evidence, constructed Ambiguities, and Candidate Claims is mirrored by those briefs’ dependency sections ([EA-0004](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:110), [EA-0005](/home/rimo/projects/EvidenceAtlas/backlog/EA-0005-ambiguity_construction.md:93), [EA-0006](/home/rimo/projects/EvidenceAtlas/backlog/EA-0006-claim_construction.md:89)). External references to AJ-003/discovery docs are not independently verifiable in the packet, but the brief records the Policy Registry dependency as a belief/not yet verified, so this does not create a blocker ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:68)).

**Scope Drift**

No scope drift found. The packet includes EA-0004/EA-0005/EA-0006 corrections, but EA-0008 explicitly claims those briefs are being corrected for role consolidation ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:24)), and the edits remain at brief/dependency alignment level rather than implementation or downstream doctrine enforcement.

**In-Scope Blockers**

No IN-SCOPE BLOCKER findings.

**Finding Classification**

No findings raised.

PR decision: ADVANCE  
Scope drift warning: no — related brief corrections are claimed by this artifact and stay within brief-stage alignment.

LOG SUMMARY: NO OBJECTION — EA-0008 satisfies brief-stage acceptance criteria with no in-scope blockers.
EVIDENCE: A
HIGHEST-IMPACT UNCERTAINTY: The packet does not include AJ-003 itself, so external architecture-journal support for the role/policy consolidation is accepted only as represented in these shown artifacts.
OpenAI Codex v0.142.5
--------
workdir: /home/rimo/projects/EvidenceAtlas
model: gpt-5.5
provider: openai
approval: never
sandbox: read-only
reasoning effort: high
reasoning summaries: none
session id: 019f73b1-d534-7052-8a04-557f4b5354ed
--------
user
Reviewer task:

SCOPE CONTRACT
  Assess this artifact against the STATED SCOPE of this stage/PR — the Expected Stage
  Output below and what the artifacts actually claim — NOT against an ideal final system.
  A capability the artifacts do not claim to provide is OUT-OF-SCOPE, not a defect.
  The following are OUT-OF-SCOPE BACKLOG unless THIS artifact explicitly claims to provide
  them: formal approval-binding enforcement; rollback correctness; COMMIT_BOUND/
  WORKSPACE_BOUND enforcement; JSON Schema validation; CI validation; exact
  decision-integrity; per-feature decision ledgers; autonomous approval; enabled hooks.

YOUR TASK — answer these five questions using only the evidence in the packet:
  1. Acceptance criteria: Does the artifact satisfy each of its stated acceptance criteria?
     Cite evidence for each criterion (or note its absence).
  2. Claim support: Are universal or strong claims (all, every, never, always, no X) in the
     artifact supported by evidence in the packet? Any unverifiable strong claim is a candidate
     finding only if it affects acceptance, scope, safety, decision integrity, or the artifact's
     stated guarantees.
  3. Scope drift: Is there any change beyond the stated scope boundary? (Files not in the
     "What changes" list; behavior changes not in the intent; downstream doctrine modified
     rather than read.)
  4. In-scope blockers: Are there facts that, if left in, would make the artifact wrong,
     unsafe, or internally contradictory?
  5. Finding classification: Classify every finding you raise as exactly one of the five
     TRIAGE RULE categories below.

TRIAGE RULE — classify EVERY finding as exactly one of:
  IN-SCOPE BLOCKER         breaks the stated goal; creates a FALSE CLAIM in this artifact;
                           weakens the advisory/read-only/human-gated guarantees; prevents
                           the work from running; or violates an explicit safety constraint.
  IN-SCOPE NON-BLOCKER     improves it but is not required for this PR.
  OUT-OF-SCOPE BACKLOG     valid, but belongs to a future feature / stronger guarantee.
  REJECTED                 conflicts with the stated scope or Codeos philosophy.
  SELF-REFERENCE /         review records that are stale because of the previous round's
  REVIEW-BOOKKEEPING       own existence (causal loop); not a real artifact defect.
  Base the PR decision ONLY on IN-SCOPE BLOCKER findings. An OUT-OF-SCOPE BACKLOG finding
  must NOT cause DO NOT ADVANCE unless this artifact FALSELY CLAIMS to solve it.

WHAT NOT TO DO
  - Do not flag style or wording issues as blockers unless the wording creates a false claim,
    contradiction, parser breakage, or wrong governance instruction.
  - Do not re-review unchanged full context when the packet is in delta mode.
  - Do not treat local-only review history as a blocker unless the artifact falsely
    claims the review artifacts are committed/durable.

INSTRUCTIONS
  If this is a resumed session, ignore any earlier-session conclusions unless they are
  re-established by THIS packet; assess only the evidence above, pinned to this commit.
  Give a focused assessment of this artifact against the stated scope, acceptance criteria,
  and evidence in this packet. Rank findings by severity. Suggest a better design only when
  needed to explain a required fix for an IN-SCOPE BLOCKER.

  Limit findings to the top 3 IN-SCOPE BLOCKERS. Additional non-blocking observations may be
  summarized in one short paragraph only if useful.

  For EACH finding emit:
    Finding: / Severity: High|Medium|Low / Classification: <one of the TRIAGE RULE labels>
    Evidence: <file/line> / Why: <short> / Required action: fix now|optional fix|backlog|reject
    Scope reason: <why it does/does not belong to this PR's scope>
  Then emit:
    PR decision: ADVANCE | REQUEST CHANGES | DO NOT ADVANCE   (based ONLY on in-scope blockers)
    Scope drift warning: yes|no — <is anything pulling this PR beyond its stated scope?>
  Then on the LAST three lines emit exactly (map ADVANCE->NO OBJECTION,
  REQUEST CHANGES->CHANGES ADVISED, DO NOT ADVANCE->DO NOT ADVANCE):
    LOG SUMMARY: <NO OBJECTION | CHANGES ADVISED | DO NOT ADVANCE | UNCLASSIFIED> — <single most important point>
      (use UNCLASSIFIED if you genuinely cannot classify the artifact safely)
    EVIDENCE: <A|B|C|D|E>
    HIGHEST-IMPACT UNCERTAINTY: <one sentence — what single thing, if wrong, most affects this assessment>

  Evidence grade — the grade describes what the assessment rests on, not reviewer confidence:
    A — Directly verified in the artifact, diff, or output shown in the packet
    B — Verified with multiple direct pieces of evidence, but coverage is not complete
    C — Partially verified, partially inferred from structure or context
    D — Mostly inferred from structure or indirect evidence
    E — Hypothesis or very limited basis — little to no direct evidence


PACKET MANIFEST
  generated: 2026-07-18T05:27:41Z
  task_prompt: /home/rimo/projects/Codeos/prompts/codeos-reviewer-task.md (4959 bytes)
  review_content_bytes: 32859
  estimated_review_tokens: ~8214
  budget_status: OK
  packet_mode: full
  delta_base: none
  items:
    - path: backlog/EA-0008-knowledge_review.md
      mode: full_file
      bytes: 6199
      sha256: fcf0d671aca1237a3430a9be76020959719c12e263f1f37078832a750eaa1efb
    - path: backlog/EA-0004-evidence_extraction.md
      mode: full_file
      bytes: 11079
      sha256: 42739674a4d4ca824c8d90b2121736e82f9724687eb138a1574a5b71c03b658a
    - path: backlog/EA-0005-ambiguity_construction.md
      mode: full_file
      bytes: 7980
      sha256: a4134a75cdf2bdaf1eaad55943eb2ab0def9c96cac5da9cd595dfe105f2cb85a
    - path: backlog/EA-0006-claim_construction.md
      mode: full_file
      bytes: 7601
      sha256: 47c1199b1410ae2e550ba742141e6c717cddb3bacb92d95db946cf1c9339d080
    - path: (diff)
      mode: full_file
      bytes: 0

REVIEW CONTEXT
  Feature:                knowledge_review
  Stage:                  brief
  Branch:                 main
  Base commit:            (no base pin)
  Review commit:          aa5be800de44b6dd7ac02a88eddb163baf5d85ff (+ uncommitted workspace changes)
  Current approved stage: n/a (non-numeric stage)
  Evidence coverage:      FULL_COVERAGE
  Workspace dirty:        yes (uncommitted changes at review time)

DBA RULES RELEVANT TO THIS STAGE
  - Human approval is required for every stage transition; you are advisory only.
  - Memory is not truth — assess only what is provided, pinned to the review commit.
  - Implementation must trace to approved artifacts; no behavior beyond intent+contract+schema.
  - No events outside the approved event schema; no hidden behavior.

STAGE-SPECIFIC CHECKS
  - problem clearly stated; scope explicitly bounded; no implementation detail; ready to become a Stage 1 Intent; value/risk/guardrail present.

EXPECTED STAGE OUTPUT
  Feature Brief — problem, upgrade, bounded scope, proposed artifact(s), value/risk/guardrail; a candidate for Stage 1, not yet approved; no implementation detail.

ARTIFACTS TO REVIEW
  --- backlog/EA-0008-knowledge_review.md (sha256: fcf0d671aca1237a3430a9be76020959719c12e263f1f37078832a750eaa1efb, visibility: shown) ---
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
    brief_last_updated: 2026-07-17
    stage1_started:

  --- backlog/EA-0004-evidence_extraction.md (sha256: 42739674a4d4ca824c8d90b2121736e82f9724687eb138a1574a5b71c03b658a, visibility: shown) ---
    # Feature Brief: EA-0004 — Evidence Extraction
    
    **Slug**: evidence_extraction
    **Type**: F-type
    **Refines**: n/a
    **Tier**: 0 — Foundational (fourth domain feature; depends only on EA-0003)
    **Status**: BRIEF-DRAFT
    
    ---
    
    ## Problem / Need
    
    A research corpus is just collected material — nobody can yet point to which passage
    supports which idea, or why it was worth collecting at all. Without this feature, every
    downstream stage would have to independently rediscover relevant passages, interpret them,
    and reconstruct why they matter to the investigation: evidence selection becomes
    inconsistent across attempts, traceability back to source material becomes fragile, and
    claim construction would have to start from raw documents instead of explicit, reviewable
    evidence.
    
    ## Primary Actor
    
    **Correction (2026-07-18, per Architecture Journal AJ-003):** the actor for this feature is
    the **Knowledge Reviewer** — a single role that also covers what EA-0005 and EA-0006
    separately called "Ambiguity Reviewer" and "Claim Reviewer." (This section previously named
    a standalone "Evidence Reviewer"; that name is retired in favor of the unified role.) The
    Knowledge Reviewer's question here specifically is whether a proposed candidate evidence
    item is suitable to enter the project's evidence base — a different question from what the
    same role asks when reviewing a claim or an ambiguity, but the same role, not a separate
    actor. Today, without this feature, that evaluation can't happen at all — the reviewer
    would have to search raw documents, choose passages, interpret them, and reconstruct
    relevance themselves, which is exactly the duplicated, inconsistent work this feature
    exists to remove.
    
    ## Core Outcome (informal)
    
    The Knowledge Reviewer can efficiently determine whether a proposed candidate evidence item
    is suitable to become part of the project's evidence base — without having to reconstruct
    the research process or rediscover the supporting material themselves. The feature has
    already done the expensive preparation (locating the passage, capturing it faithfully,
    interpreting it, and explaining why it belongs to the investigation); the reviewer's job
    becomes evaluation, not investigation. Concretely, that single "fit for acceptance"
    decision rests on three distinguishable questions later Stage 1/2 work should keep
    separate: was the right passage *selected* for this Research Question, does the
    *interpretation* stay grounded in what the passage actually says, and does that
    interpretation actually *advance* the Research Question it's linked to. This feature
    doesn't decide any of the three — it produces evidence structured so the Knowledge
    Reviewer, through EA-0008 (Knowledge Review), can decide efficiently.
    
    ## Design Tensions and Open Questions
    
    1. **Should this be one feature, or split into passage-selection and interpretation?**
       [Resolved: one feature. The deciding test is the same one that justified splitting
       EA-0002 from EA-0003: does the earlier stopping point have independent actor value? A
       Research Plan does — an editor can review a strategy before spending resources. A pile
       of highlighted-but-uninterpreted passages doesn't — no reviewer benefits from evaluating
       spans of text with no sense of what they're claimed to support. A future split would be
       scalability-driven (very large corpora, separate retrieval models, passage reuse across
       many interpretations at scale), not a mechanical-vs-interpretive one — not applicable for
       v1.]
    2. **Where's the line between this feature's self-verification and EA-0008's (Knowledge
       Review's) acceptance decision?** [Resolved as a principle: this feature may only verify
       narrow, structural/grounding properties — the source belongs to the approved corpus, the
       locator resolves to the cited passage, the excerpt is faithful and unaltered (truncation
       disclosed), sufficient context was captured, required fields are present, the
       interpretation doesn't visibly introduce facts absent from the source, and
       duplicate/overlapping records are flagged. It may never assert that a candidate is
       *accepted* — only that it's structurally complete and apparently grounded. The "visibly
       introduce unsupported facts" check sits closest to the line, since it requires some
       semantic comparison, not pure structure-checking — flagged for Stage 1/2 to tighten if
       needed. Everything about substantive acceptance (does the interpretation actually hold
       up, is it too broad, are qualifications missing, accept/reject/return-for-revision)
       belongs to EA-0008 (Knowledge Review), owned by the Knowledge Reviewer. These are
       recorded here as **assumptions requiring validation by that brief**, not decisions this
       feature owns — this feature produces Candidate Evidence; only EA-0008 produces Accepted
       Evidence.]
    3. **What happens when no passage can be found for a Research Question?** [Resolved:
       report it explicitly as an investigation finding, not a retrieval failure — e.g. "no
       candidate evidence identified in the approved corpus for RQ-3." This says nothing about
       reality, only about what this corpus contains, and is itself valuable information rather
       than an error to hide.]
    4. **What happens when one passage is relevant to multiple Research Questions?**
       [Resolved: extract once, link to many — a single candidate evidence item can reference
       several Research Questions rather than being duplicated per question. Duplicating it
       would create multiple copies of the same evidence that could drift independently, the
       same "multiple mutable sources of truth" risk already flagged architecturally in
       `docs/solution-discovery-evidenceatlas.md`.]
    5. **How should corroboration between independent sources be distinguished from mechanical
       duplication?** [Resolved as a principle: this feature may recognize mechanical
       duplication (e.g. a wire-service article republished verbatim) but must not collapse
       independent agreement between genuinely distinct sources into "duplicate" — that
       agreement is valuable signal for later stages, not redundancy. This feature doesn't
       reason about *what* corroboration means or aggregate it; it only avoids destroying the
       distinction. **Open nuance:** telling "mechanically identical/republished" apart from
       "independently produced but agreeing" is itself a judgment call that isn't fully
       specified here — left for Stage 2 to define concretely.]
    6. **Does this feature do any new source discovery?** [Resolved: no, hard boundary. It
       operates only over the already-approved Research Corpus from EA-0003 — no web search,
       no new crawling, no "just one more source." Crossing this boundary would make the
       provenance chain impossible to reconstruct.]
    7. **Naming:** the feature name "Evidence Extraction" stays workable (it matches the
       discovery doc's existing vocabulary — Evidence is already defined as excerpt +
       interpretation), but its *output* should use provisional language (e.g. "Candidate
       Evidence") rather than implying accepted evidence emerges automatically.
    
    ## Suspected Dependencies
    
    Upstream: EA-0003 (Research Corpus + Research Execution Report) only.
    
    Downstream (hard): EA-0008 (Knowledge Review) consumes Candidate Evidence directly, and its
    Knowledge Reviewer evaluates it. The accept/reject/return-for-revision behavior, and the
    expectation that any revised interpretation produces a traceable new version rather than a
    silent rewrite, are owned by EA-0008, not this feature.
    
    **Correction (2026-07-17, during EA-0006 Round 0; actor/feature names updated 2026-07-18
    per AJ-003):** Claim Construction (EA-0006) does **not** consume Candidate Evidence
    directly, despite what an earlier version of this section said. It consumes **Accepted
    Evidence**, the artifact state produced once EA-0008 (Knowledge Review) accepts a
    candidate — otherwise unreviewed, possibly-hallucinated candidates could influence claim
    synthesis before the human acceptance step meant to catch that. The chain is: this feature
    produces Candidate Evidence → EA-0008 (Knowledge Review) produces Accepted Evidence →
    EA-0006 (Claim Construction) consumes Accepted Evidence. EA-0006's dependency on this
    feature's output is indirect, mediated through EA-0008's acceptance decision, not a direct
    dependency on Candidate Evidence itself.
    
    Downstream (soft): EA-0005 (Ambiguity Construction) is the deliberate exception to the
    correction above — its pre-claim path explicitly accepts manually-referred Candidate
    Evidence pairs directly from this feature, without requiring EA-0008's acceptance first,
    since that path is explicitly analytical/provisional (it can conclude "no real conflict" or
    "insufficient context") and doesn't promote those candidates into the accepted evidence
    base. Not a hard dependency in the sense of being required for this feature to run, but
    worth keeping in mind, since `initiate.md`'s original contradiction-handling flow only
    considered ambiguity emerging at the claim level.
    
    ## Rough Scope Notes
    
    In scope (rough): locating candidate passages relevant to the approved Research Questions,
    within the approved Research Corpus only; capturing exact excerpts with resolvable
    provenance and sufficient context; producing a bounded interpretation per passage plus a
    short selection rationale explaining why it belongs to the investigation; linking each
    candidate evidence item to one or more Research Questions; running the narrow structural/
    grounding preflight checks listed above; explicitly reporting when no candidate evidence is
    found for a Research Question; recognizing mechanical duplication while preserving
    corroboration signal; emitting results as provisional Candidate Evidence pending
    acceptance.
    
    Out of scope (rough): any new source discovery, web search, or crawling (stays inside
    EA-0003's boundary); the substantive acceptance decision (accept/reject/revise — belongs to
    EA-0008, Knowledge Review); contradiction or ambiguity reasoning; claim
    construction; reasoning about what corroboration *means* or aggregating corroborating
    evidence (a later feature's job — this feature only preserves the distinction from
    duplication); canonical ownership of the "Evidence Category" vocabulary term (left
    intentionally open per EA-0002, for the same premature-ontology reason).
    
    ## Readiness Check
    
    - [x] The problem statement explains WHY, not HOW
    - [x] The primary actor is a human role, not "the system"
    - [x] The core outcome is stated from the actor's perspective
    - [x] At least one open question is listed (seven listed)
    - [x] Suspected dependencies are named (even if marked uncertain)
    - [x] No actor+outcome DBA form appears anywhere in this brief
    - [x] No stable guarantees or DBA scope boundaries appear in this brief
    - [x] The feature can be described without mentioning implementation technology
    - [x] (R-type only) — n/a, this is F-type
    
    **Brief status**: READY FOR STAGE 1
    
    ---
    
    <!-- METADATA -->
    brief_created: 2026-07-17
    brief_last_updated: 2026-07-18
    stage1_started:

  --- backlog/EA-0005-ambiguity_construction.md (sha256: a4134a75cdf2bdaf1eaad55943eb2ab0def9c96cac5da9cd595dfe105f2cb85a, visibility: shown) ---
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

  --- backlog/EA-0006-claim_construction.md (sha256: 47c1199b1410ae2e550ba742141e6c717cddb3bacb92d95db946cf1c9339d080, visibility: shown) ---
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

DIFF TO REVIEW (base->review, secret/size filtered)

codex
I’ll anchor this to the packet artifacts and grab line numbers from the workspace copies so the findings and acceptance notes are citeable.
exec
/bin/bash -lc "nl -ba backlog/EA-0008-knowledge_review.md | sed -n '1,180p'" in /home/rimo/projects/EvidenceAtlas
 succeeded in 0ms:
     1	# Feature Brief: EA-0008 — Knowledge Review
     2	
     3	**Slug**: knowledge_review
     4	**Type**: F-type
     5	**Refines**: n/a
     6	**Tier**: 0 — Foundational (governance feature; consumes EA-0004, EA-0005, and EA-0006
     7	directly, and recurs across the pipeline rather than firing once)
     8	**Status**: BRIEF-DRAFT
     9	
    10	---
    11	
    12	## Problem / Need
    13	
    14	Without a way to evaluate whether extracted evidence, synthesized claims, and structured
    15	ambiguities actually represent trustworthy knowledge, unreviewed or possibly-hallucinated
    16	material could silently enter the pipeline and eventually reach publication. The entire
    17	evidence-first premise of this project depends on a real checkpoint existing between "the
    18	AI produced a candidate" and "this is part of the trusted knowledge base" — right now
    19	three separate transformation features (EA-0004, EA-0005, EA-0006) each assume that
    20	checkpoint exists without any feature actually owning it.
    21	
    22	## Primary Actor
    23	
    24	The **Knowledge Reviewer** — a single role that replaces the separately-named "Evidence
    25	Reviewer," "Ambiguity Reviewer," and "Claim Reviewer" used when EA-0004, EA-0005, and
    26	EA-0006 were briefed (those briefs are being corrected to reflect this consolidation). The
    27	underlying review question still differs by what's under review — is this excerpt and
    28	interpretation faithful to its source; is this synthesis adequately supported, bounded, and
    29	decision-relevant; does this structure a genuine, decision-relevant disagreement — but it's
    30	one role asking variants of one broader question: can this be trusted as part of the
    31	knowledge base.
    32	
    33	## Core Outcome (informal)
    34	
    35	The Knowledge Reviewer can evaluate a proposed piece of knowledge — Candidate Evidence, a
    36	Candidate Claim, or a constructed Ambiguity — without needing to re-derive or reconstruct
    37	the underlying material or reasoning themselves, since the feature that produced it has
    38	already prepared it for review (excerpt plus interpretation and rationale; synthesis with
    39	supporting/limiting evidence attached; structured competing positions with their evidence).
    40	This is a recurring governance activity applied at multiple points across the pipeline as
    41	material arrives, not a single point-in-time gate.
    42	
    43	## Design Tensions and Open Questions
    44	
    45	1. **This is recurring, not a single gate.** [Resolved, per Architecture Journal AJ-003:
    46	   this feature fires repeatedly — once evidence is extracted, once claims are synthesized,
    47	   once ambiguities are constructed — under one policy umbrella, rather than being one
    48	   checkpoint that happens once per investigation.]
    49	2. **Does this feature own the accept/reject/return-for-revision decisions previously
    50	   assumed by EA-0004 and EA-0006?** [Resolved: yes. This is where those "assumptions
    51	   requiring validation" become owned decisions — accept/reject/revise on Candidate
    52	   Evidence; accept/reject/revise on Candidate Claims; accept/return-for-more-analysis on
    53	   constructed Ambiguities. This feature also owns routing a human-initiated suspected-
    54	   disagreement referral to EA-0005 (previously described as something "Gate 1" did in
    55	   EA-0004's brief).]
    56	3. **Does review of one artifact type block progress on others?** [Not resolved — must all
    57	   evidence for a Research Question be accepted before Claim Construction can run on any of
    58	   it, or can synthesis proceed incrementally as evidence is accepted in batches? A genuine
    59	   open question for Stage 1/2, not decided here.]
    60	4. **Granularity and blocking-vs-advisory are policy-driven, not structural.** [Resolved,
    61	   per AJ-003 and the discovery doc's "Policy centralization" finding: this feature consults
    62	   a not-yet-briefed Policy Registry for review strategy (per-item, per-bundle, sampled,
    63	   blocking, advisory, risk-based skipping) rather than hardcoding one strategy for every
    64	   artifact type.]
    65	
    66	## Suspected Dependencies
    67	
    68	Upstream (hard): EA-0004 (Candidate Evidence), EA-0005 (constructed Ambiguities), and
    69	EA-0006 (Candidate Claims) — all three consumed directly. Also a not-yet-briefed Policy
    70	Registry feature, consulted for review strategy — recorded as a belief, not yet verified.
    71	
    72	Note on relationship shape: this is not a simple one-directional consumption. This
    73	feature's Accepted Evidence output feeds EA-0006 (Claim Construction), which produces
    74	Candidate Claims that come back to this same feature for review — a recurring, staged
    75	back-and-forth across the pipeline, not a cycle within a single pass.
    76	
    77	Downstream (hard): EA-0006 depends on this feature's Accepted Evidence output (per the
    78	correction already made to EA-0004's brief).
    79	
    80	Downstream (soft): eventual Publishing views and EA-0009 (Publication Review, once briefed)
    81	will likely consume this feature's accepted knowledge base (Accepted Evidence, Accepted
    82	Claims, resolved Ambiguities) as their source of truth.
    83	
    84	## Rough Scope Notes
    85	
    86	In scope (rough): evaluating Candidate Evidence, Candidate Claims, and Ambiguities for
    87	trustworthiness, using the distinct question appropriate to each; owning accept/reject/
    88	return-for-revision outcomes for each; routing human-initiated disagreement referrals to
    89	Ambiguity Construction; consulting the Policy Registry for review strategy.
    90	
    91	Out of scope (rough): producing any of the underlying candidates itself (each transformation
    92	feature's own job); investigation-level approval (EA-0007's job); publication-level approval
    93	(EA-0009's job, once briefed); defining the Policy Registry itself.
    94	
    95	## Readiness Check
    96	
    97	- [x] The problem statement explains WHY, not HOW
    98	- [x] The primary actor is a human role, not "the system"
    99	- [x] The core outcome is stated from the actor's perspective
   100	- [x] At least one open question is listed (four listed)
   101	- [x] Suspected dependencies are named (even if marked uncertain)
   102	- [x] No actor+outcome DBA form appears anywhere in this brief
   103	- [x] No stable guarantees or DBA scope boundaries appear in this brief (scope notes are
   104	      informal guardrails, not formal DBA contract language)
   105	- [x] The feature can be described without mentioning implementation technology
   106	- [x] (R-type only) — n/a, this is F-type
   107	
   108	**Brief status**: READY FOR STAGE 1
   109	
   110	---
   111	
   112	<!-- METADATA -->
   113	brief_created: 2026-07-17
   114	brief_last_updated: 2026-07-17
   115	stage1_started:

exec
/bin/bash -lc "nl -ba backlog/EA-0006-claim_construction.md | sed -n '1,170p'" in /home/rimo/projects/EvidenceAtlas
exec
/bin/bash -lc "nl -ba backlog/EA-0005-ambiguity_construction.md | sed -n '1,170p'" in /home/rimo/projects/EvidenceAtlas
 succeeded in 0ms:
     1	# Feature Brief: EA-0006 — Claim Construction
     2	
     3	**Slug**: claim_construction
     4	**Type**: F-type
     5	**Refines**: n/a
     6	**Tier**: 0 — Foundational (depends on EA-0008's Accepted Evidence output — see Suspected
     7	Dependencies)
     8	**Status**: BRIEF-DRAFT
     9	
    10	---
    11	
    12	## Problem / Need
    13	
    14	Accepted evidence, even once verified as faithful to its sources, is still just a
    15	collection of individually-grounded excerpts and interpretations — nobody has yet
    16	synthesized what defensible proposition, if any, that evidence supports for a given
    17	Research Question. Without this feature, every downstream use of the evidence base
    18	(publishing, decision-brief generation) would need to re-derive that synthesis itself,
    19	inconsistently and without a reviewable intermediate record of what was concluded and why.
    20	
    21	## Primary Actor
    22	
    23	**Correction (2026-07-18, per Architecture Journal AJ-003):** the actor for this feature is
    24	the **Knowledge Reviewer** — the same unified role used for EA-0004 and EA-0005 (this
    25	section previously named a standalone future "Claim Reviewer"; that name is retired). The
    26	question the Knowledge Reviewer asks here is specifically whether a proposed Candidate
    27	Claim is sufficiently supported, bounded, and decision-relevant to enter the accepted claim
    28	base — a different question from evidence acceptance or ambiguity approval, but asked by
    29	the same role. Today, without this feature, that person would have no synthesized
    30	proposition to evaluate at all — they'd have to read raw accepted evidence and construct an
    31	interpretation themselves before they could even begin reviewing one.
    32	
    33	## Core Outcome (informal)
    34	
    35	The Knowledge Reviewer can evaluate a proposed, defensible proposition synthesized from
    36	accepted evidence — with its supporting and limiting evidence, scope, qualifiers, and
    37	synthesis rationale already attached — rather than having to synthesize it themselves
    38	before they can review it. When the accepted evidence for a Research Question can't be
    39	responsibly reconciled into any claim, they instead see that outcome recorded honestly
    40	(and, where relevant, referred to Ambiguity Construction) rather than a forced or
    41	overreaching proposition.
    42	
    43	## Design Tensions and Open Questions
    44	
    45	1. **Construction vs. approval — same split as Evidence Extraction / Knowledge Review.**
    46	   [Resolved: this feature only produces Candidate Claims; it never approves, rejects, or
    47	   decides a claim is authoritative, and never silently revises a claim after a reviewer has
    48	   looked at it. EA-0008 (Knowledge Review) owns that decision. The independent-actor-value
    49	   test gives the same answer as before — a Candidate Claim has clear review value on its
    50	   own, and "accepted claim" is a materially different state produced by a distinct human
    51	   judgment.]
    52	2. **Does this feature consume raw Candidate Evidence or EA-0008-accepted Evidence?**
    53	   [Resolved: Accepted Evidence only. Operating on unreviewed Candidate Evidence would let
    54	   a hallucinated or misinterpreted candidate influence synthesis before the human
    55	   acceptance step meant to catch exactly that. This corrects EA-0004's brief, which
    56	   previously said Claim Construction consumes Candidate Evidence directly — see the
    57	   correction note added there.]
    58	3. **Does one Research Question resolve to exactly one Claim?** [Resolved: no — a Research
    59	   Question can produce zero, one, or multiple Claims, addressing different dimensions
    60	   (magnitude, mechanism, boundary conditions, risks, evidence limitations) that coexist
    61	   and qualify each other rather than conflict. Multiple claims on the same Research
    62	   Question are not automatically an ambiguity — they become one only when the
    63	   interpretations genuinely compete and that competing relationship itself needs
    64	   structuring (Ambiguity Construction's job, not this feature's). Legitimate outcomes for
    65	   a Research Question also include: no accepted evidence exists yet, the evidence is
    66	   insufficient to synthesize anything defensible, or the result is an Ambiguity referral
    67	   with no accompanying Claim at all.]
    68	4. **Does canonical ownership of "Evidence Category" finally land here?** [Resolved: no,
    69	   deferred again — this would conflate what a piece of evidence *is* with what can be
    70	   *synthesized from it*. Instead, this feature originates a narrower, more load-bearing
    71	   vocabulary: the **Claim-Evidence relationship** (supports, opposes, qualifies, limits,
    72	   contextualizes, insufficient-to-determine) — how accepted Evidence bears on a specific
    73	   Candidate Claim. Evidence-intrinsic characteristics (empirical study, official
    74	   statistics, regulation, vendor case study, etc.) belong with the Evidence model or
    75	   EA-0008's acceptance layer instead, whenever that gets defined.]
    76	5. **Relationship to existing Ambiguities.** [Not resolved — left open rather than forced.
    77	   Could a later Claim Construction run (e.g. against updated evidence) reference an
    78	   already-constructed Ambiguity to properly scope or qualify a new claim around a known
    79	   disputed sub-condition? Plausible, but not required for this feature to function, and
    80	   deliberately left as a later dependency question rather than decided now.]
    81	
    82	## Suspected Dependencies
    83	
    84	Upstream (hard): EA-0008 (Knowledge Review)'s **Accepted Evidence** output — not Candidate
    85	Evidence directly (see resolution #2 above). This feature also consumes Research Questions
    86	and their upstream traceability context (from EA-0002's Research Plan, carried through
    87	EA-0008's acceptance step).
    88	
    89	Downstream (hard): EA-0008 (Knowledge Review) consumes Candidate Claims directly, and its
    90	Knowledge Reviewer owns accept/reject/return-for-revision on them.
    91	
    92	Downstream (hard, existing): EA-0005 (Ambiguity Construction) consumes referrals from this
    93	feature when synthesis can't reconcile competing interpretations for a Research Question —
    94	already established when EA-0005 was briefed.
    95	
    96	Downstream (soft, open): whether a later Claim Construction run should be able to reference
    97	an existing Ambiguity when scoping a new claim (see Design Tension #5) — not decided.
    98	
    99	## Rough Scope Notes
   100	
   101	In scope (rough): synthesizing zero or more Candidate Claims per Research Question from
   102	Accepted Evidence (produced via EA-0008); attaching supporting and limiting evidence to
   103	each; recording scope, qualifiers, and synthesis rationale; originating the Claim-Evidence
   104	relationship vocabulary; referring irreconcilable synthesis results to Ambiguity
   105	Construction.
   106	
   107	Out of scope (rough): claim approval or rejection, and evidence acceptance (both EA-0008's
   108	job); the canonical Evidence Category taxonomy (deferred, likely belongs with the Evidence
   109	model or EA-0008); adjudicating or resolving Ambiguities; forcing exactly one claim per
   110	Research Question, or forcing any claim to be produced when the evidence doesn't support
   111	one.
   112	
   113	## Readiness Check
   114	
   115	- [x] The problem statement explains WHY, not HOW
   116	- [x] The primary actor is a human role, not "the system"
   117	- [x] The core outcome is stated from the actor's perspective
   118	- [x] At least one open question is listed (five listed)
   119	- [x] Suspected dependencies are named (even if marked uncertain)
   120	- [x] No actor+outcome DBA form appears anywhere in this brief
   121	- [x] No stable guarantees or DBA scope boundaries appear in this brief (scope notes are
   122	      informal guardrails, not formal DBA contract language)
   123	- [x] The feature can be described without mentioning implementation technology
   124	- [x] (R-type only) — n/a, this is F-type
   125	
   126	**Brief status**: READY FOR STAGE 1
   127	
   128	---
   129	
   130	<!-- METADATA -->
   131	brief_created: 2026-07-17
   132	brief_last_updated: 2026-07-18
   133	stage1_started:

 succeeded in 0ms:
     1	# Feature Brief: EA-0005 — Ambiguity Construction
     2	
     3	**Slug**: ambiguity_construction
     4	**Type**: F-type
     5	**Refines**: n/a
     6	**Tier**: 0 — Foundational (depends on EA-0004 directly; EA-0006, briefed after this
     7	feature, supplies its second input path — see Suspected Dependencies)
     8	**Status**: BRIEF-DRAFT
     9	
    10	---
    11	
    12	## Problem / Need
    13	
    14	Evidence — and eventually claims — bearing on the same Research Question can embody
    15	genuinely incompatible positions. Without a way to structure that disagreement explicitly,
    16	the pipeline either forces a single conclusion that quietly discards a real, decision-
    17	relevant dispute, or loses track of the disagreement entirely because nothing ever recorded
    18	it. Both failure modes undermine the "preserve uncertainty, don't hide it" principle this
    19	project exists to uphold.
    20	
    21	## Primary Actor
    22	
    23	**Correction (2026-07-18, per Architecture Journal AJ-003):** the actor for this feature is
    24	the **Knowledge Reviewer** — the same unified role used for EA-0004 and EA-0006 (this
    25	section previously named a standalone "Ambiguity Reviewer"; that name is retired). The
    26	question the Knowledge Reviewer asks here is specifically whether a proposed Ambiguity
    27	accurately structures a real, decision-relevant disagreement — including the competing
    28	positions, the evidence behind each, and the conditions that distinguish them — a different
    29	question from evidence acceptance or claim approval, but asked by the same role rather than
    30	a separate actor. (Tracked in Architecture Journal AJ-002.)
    31	
    32	## Core Outcome (informal)
    33	
    34	The Knowledge Reviewer can evaluate a referred, suspected disagreement without having to
    35	reconstruct why it was flagged or manually cross-reference the underlying evidence
    36	themselves. When a genuine unresolved disagreement exists, they receive a structured
    37	representation of the competing positions, the evidence supporting each, and the
    38	assumptions or conditions that distinguish them. When it doesn't — the referral turns out
    39	to reflect a scope, population, timeframe, or definitional difference rather than a real
    40	conflict — they receive that finding instead, rather than a manufactured Ambiguity.
    41	
    42	## Design Tensions and Open Questions
    43	
    44	1. **Two entry paths, one canonical artifact.** [Resolved: this feature accepts (a) a
    45	   human-initiated referral — the Knowledge Reviewer, while evaluating evidence through
    46	   EA-0008 (Knowledge Review), notices two Candidate Evidence items that may express
    47	   incompatible positions and refers them, without resolving the question themselves; and
    48	   (b) an automatic referral
    49	   from Claim Construction, when synthesis attempts to reconcile competing interpretations
    50	   and cannot. Both converge on one Ambiguity artifact type, which records which path
    51	   produced it.]
    52	2. **Referral vs. detection — where's the boundary?** [Resolved: this feature never
    53	   searches the evidence base or claim set for disagreement on its own. It only evaluates
    54	   and structures a bounded referral it's given. Corpus-wide or pairwise automated
    55	   conflict detection is explicitly deferred to a possible future feature, justified only if
    56	   review throughput becomes a demonstrated bottleneck — not in scope for v1.]
    57	3. **What does a referral actually establish?** [Resolved: only a *suspected* disagreement,
    58	   never a confirmed one. This feature's job is to determine whether the referred items
    59	   represent (a) a genuine unresolved ambiguity, (b) a difference that's actually resolved
    60	   by scope, population, timeframe, or definition — conditionally compatible, not truly in
    61	   conflict — (c) no real conflict at all, or (d) insufficient context to assess yet. **No
    62	   forced reconciliation, in either direction:** the feature must not manufacture false
    63	   consensus just to avoid producing an Ambiguity, and it must not manufacture an Ambiguity
    64	   just because a referral was made, if the evidence doesn't actually support one. A
    65	   reviewer referring two items does not, by itself, create a canonical ambiguity.]
    66	4. **Is Ambiguity mutually exclusive with Claim?** [Resolved: no. A Claim and a linked
    67	   residual Ambiguity can coexist for the same investigation at different granularity —
    68	   e.g. a general claim holds, with a narrower disputed sub-condition recorded alongside
    69	   it rather than either silently dropped or forced to block the general claim.]
    70	5. **What happens after a referral is assessed as (d) "insufficient context"?** [Not
    71	   resolved — genuinely open, unlike #1-4 above. Does the referral stay pending until more
    72	   evidence arrives naturally (e.g. from a later Corpus Construction or Evidence Extraction
    73	   pass), does it require the referring party to actively supply more context before
    74	   re-submission, or does it simply expire unrecorded? Left for Stage 1/2 to decide.]
    75	
    76	## Suspected Dependencies
    77	
    78	**Direct input dependencies:**
    79	- EA-0004 (Candidate Evidence) — available now, for human-referred pre-claim cases.
    80	- Claim Construction's outputs (Claims, and failed/irreconcilable-synthesis referrals) —
    81	  not yet briefed. This feature requires at least one supported referral input to operate;
    82	  in v1 it can run directly against EA-0004 Candidate Evidence, and once Claim Construction
    83	  exists, its outputs become an *additional* direct input path — this is deliberately not
    84	  phrased as a hard blocking dependency on a feature that doesn't exist yet.
    85	
    86	**Invocation sources (distinct from the data itself):**
    87	- The Knowledge Reviewer manually flagging selected Candidate Evidence while evaluating it
    88	  through EA-0008 (Knowledge Review) — meaning EA-0008 isn't only an accept/reject
    89	  checkpoint, it's also a routing point for suspected disagreement. (Another input to
    90	  AJ-001's editorial-consolidation tracking, and now reflected in EA-0008's own brief.)
    91	- Claim Construction (EA-0006) automatically referring a synthesis it cannot reconcile.
    92	
    93	**Downstream (hard, now briefed):** EA-0008 (Knowledge Review) consumes constructed
    94	Ambiguities directly — the Knowledge Reviewer's approval of an Ambiguity is owned there, not
    95	by this feature.
    96	
    97	**Downstream (soft, not yet briefed):** eventual Publishing views (e.g. a Reality Check's
    98	ambiguity framing) likely consume this feature's output — not confirmed, since Publishing
    99	isn't briefed yet.
   100	
   101	## Rough Scope Notes
   102	
   103	In scope (rough): evaluating a bounded referral from either entry path; determining whether
   104	the referred items represent genuine ambiguity, conditional compatibility, no real
   105	conflict, or insufficient context to assess; constructing a reviewable representation of
   106	competing positions, their supporting evidence, and the assumptions/conditions that
   107	distinguish them, when genuine ambiguity is found.
   108	
   109	Out of scope (rough): claim construction itself; corpus-wide or pairwise automated conflict
   110	detection, or independently searching for disagreements; adjudicating which position is
   111	correct; recommending which side a decision-maker should follow; silently rewriting Claims
   112	or Candidate Evidence to remove a disagreement; forced reconciliation in either direction
   113	(manufacturing consensus, or manufacturing an ambiguity without genuine evidence of one).
   114	
   115	## Readiness Check
   116	
   117	- [x] The problem statement explains WHY, not HOW
   118	- [x] The primary actor is a human role, not "the system"
   119	- [x] The core outcome is stated from the actor's perspective
   120	- [x] At least one open question is listed (five listed; #1-4 resolved as principles, #5
   121	      genuinely open)
   122	- [x] Suspected dependencies are named (even if marked uncertain)
   123	- [x] No actor+outcome DBA form appears anywhere in this brief
   124	- [x] No stable guarantees or DBA scope boundaries appear in this brief (scope notes are
   125	      informal guardrails, not formal DBA contract language)
   126	- [x] The feature can be described without mentioning implementation technology
   127	- [x] (R-type only) — n/a, this is F-type
   128	
   129	**Brief status**: READY FOR STAGE 1
   130	
   131	---
   132	
   133	<!-- METADATA -->
   134	brief_created: 2026-07-17
   135	brief_last_updated: 2026-07-18
   136	stage1_started:

exec
/bin/bash -lc "nl -ba backlog/EA-0004-evidence_extraction.md | sed -n '1,190p'" in /home/rimo/projects/EvidenceAtlas
 succeeded in 0ms:
     1	# Feature Brief: EA-0004 — Evidence Extraction
     2	
     3	**Slug**: evidence_extraction
     4	**Type**: F-type
     5	**Refines**: n/a
     6	**Tier**: 0 — Foundational (fourth domain feature; depends only on EA-0003)
     7	**Status**: BRIEF-DRAFT
     8	
     9	---
    10	
    11	## Problem / Need
    12	
    13	A research corpus is just collected material — nobody can yet point to which passage
    14	supports which idea, or why it was worth collecting at all. Without this feature, every
    15	downstream stage would have to independently rediscover relevant passages, interpret them,
    16	and reconstruct why they matter to the investigation: evidence selection becomes
    17	inconsistent across attempts, traceability back to source material becomes fragile, and
    18	claim construction would have to start from raw documents instead of explicit, reviewable
    19	evidence.
    20	
    21	## Primary Actor
    22	
    23	**Correction (2026-07-18, per Architecture Journal AJ-003):** the actor for this feature is
    24	the **Knowledge Reviewer** — a single role that also covers what EA-0005 and EA-0006
    25	separately called "Ambiguity Reviewer" and "Claim Reviewer." (This section previously named
    26	a standalone "Evidence Reviewer"; that name is retired in favor of the unified role.) The
    27	Knowledge Reviewer's question here specifically is whether a proposed candidate evidence
    28	item is suitable to enter the project's evidence base — a different question from what the
    29	same role asks when reviewing a claim or an ambiguity, but the same role, not a separate
    30	actor. Today, without this feature, that evaluation can't happen at all — the reviewer
    31	would have to search raw documents, choose passages, interpret them, and reconstruct
    32	relevance themselves, which is exactly the duplicated, inconsistent work this feature
    33	exists to remove.
    34	
    35	## Core Outcome (informal)
    36	
    37	The Knowledge Reviewer can efficiently determine whether a proposed candidate evidence item
    38	is suitable to become part of the project's evidence base — without having to reconstruct
    39	the research process or rediscover the supporting material themselves. The feature has
    40	already done the expensive preparation (locating the passage, capturing it faithfully,
    41	interpreting it, and explaining why it belongs to the investigation); the reviewer's job
    42	becomes evaluation, not investigation. Concretely, that single "fit for acceptance"
    43	decision rests on three distinguishable questions later Stage 1/2 work should keep
    44	separate: was the right passage *selected* for this Research Question, does the
    45	*interpretation* stay grounded in what the passage actually says, and does that
    46	interpretation actually *advance* the Research Question it's linked to. This feature
    47	doesn't decide any of the three — it produces evidence structured so the Knowledge
    48	Reviewer, through EA-0008 (Knowledge Review), can decide efficiently.
    49	
    50	## Design Tensions and Open Questions
    51	
    52	1. **Should this be one feature, or split into passage-selection and interpretation?**
    53	   [Resolved: one feature. The deciding test is the same one that justified splitting
    54	   EA-0002 from EA-0003: does the earlier stopping point have independent actor value? A
    55	   Research Plan does — an editor can review a strategy before spending resources. A pile
    56	   of highlighted-but-uninterpreted passages doesn't — no reviewer benefits from evaluating
    57	   spans of text with no sense of what they're claimed to support. A future split would be
    58	   scalability-driven (very large corpora, separate retrieval models, passage reuse across
    59	   many interpretations at scale), not a mechanical-vs-interpretive one — not applicable for
    60	   v1.]
    61	2. **Where's the line between this feature's self-verification and EA-0008's (Knowledge
    62	   Review's) acceptance decision?** [Resolved as a principle: this feature may only verify
    63	   narrow, structural/grounding properties — the source belongs to the approved corpus, the
    64	   locator resolves to the cited passage, the excerpt is faithful and unaltered (truncation
    65	   disclosed), sufficient context was captured, required fields are present, the
    66	   interpretation doesn't visibly introduce facts absent from the source, and
    67	   duplicate/overlapping records are flagged. It may never assert that a candidate is
    68	   *accepted* — only that it's structurally complete and apparently grounded. The "visibly
    69	   introduce unsupported facts" check sits closest to the line, since it requires some
    70	   semantic comparison, not pure structure-checking — flagged for Stage 1/2 to tighten if
    71	   needed. Everything about substantive acceptance (does the interpretation actually hold
    72	   up, is it too broad, are qualifications missing, accept/reject/return-for-revision)
    73	   belongs to EA-0008 (Knowledge Review), owned by the Knowledge Reviewer. These are
    74	   recorded here as **assumptions requiring validation by that brief**, not decisions this
    75	   feature owns — this feature produces Candidate Evidence; only EA-0008 produces Accepted
    76	   Evidence.]
    77	3. **What happens when no passage can be found for a Research Question?** [Resolved:
    78	   report it explicitly as an investigation finding, not a retrieval failure — e.g. "no
    79	   candidate evidence identified in the approved corpus for RQ-3." This says nothing about
    80	   reality, only about what this corpus contains, and is itself valuable information rather
    81	   than an error to hide.]
    82	4. **What happens when one passage is relevant to multiple Research Questions?**
    83	   [Resolved: extract once, link to many — a single candidate evidence item can reference
    84	   several Research Questions rather than being duplicated per question. Duplicating it
    85	   would create multiple copies of the same evidence that could drift independently, the
    86	   same "multiple mutable sources of truth" risk already flagged architecturally in
    87	   `docs/solution-discovery-evidenceatlas.md`.]
    88	5. **How should corroboration between independent sources be distinguished from mechanical
    89	   duplication?** [Resolved as a principle: this feature may recognize mechanical
    90	   duplication (e.g. a wire-service article republished verbatim) but must not collapse
    91	   independent agreement between genuinely distinct sources into "duplicate" — that
    92	   agreement is valuable signal for later stages, not redundancy. This feature doesn't
    93	   reason about *what* corroboration means or aggregate it; it only avoids destroying the
    94	   distinction. **Open nuance:** telling "mechanically identical/republished" apart from
    95	   "independently produced but agreeing" is itself a judgment call that isn't fully
    96	   specified here — left for Stage 2 to define concretely.]
    97	6. **Does this feature do any new source discovery?** [Resolved: no, hard boundary. It
    98	   operates only over the already-approved Research Corpus from EA-0003 — no web search,
    99	   no new crawling, no "just one more source." Crossing this boundary would make the
   100	   provenance chain impossible to reconstruct.]
   101	7. **Naming:** the feature name "Evidence Extraction" stays workable (it matches the
   102	   discovery doc's existing vocabulary — Evidence is already defined as excerpt +
   103	   interpretation), but its *output* should use provisional language (e.g. "Candidate
   104	   Evidence") rather than implying accepted evidence emerges automatically.
   105	
   106	## Suspected Dependencies
   107	
   108	Upstream: EA-0003 (Research Corpus + Research Execution Report) only.
   109	
   110	Downstream (hard): EA-0008 (Knowledge Review) consumes Candidate Evidence directly, and its
   111	Knowledge Reviewer evaluates it. The accept/reject/return-for-revision behavior, and the
   112	expectation that any revised interpretation produces a traceable new version rather than a
   113	silent rewrite, are owned by EA-0008, not this feature.
   114	
   115	**Correction (2026-07-17, during EA-0006 Round 0; actor/feature names updated 2026-07-18
   116	per AJ-003):** Claim Construction (EA-0006) does **not** consume Candidate Evidence
   117	directly, despite what an earlier version of this section said. It consumes **Accepted
   118	Evidence**, the artifact state produced once EA-0008 (Knowledge Review) accepts a
   119	candidate — otherwise unreviewed, possibly-hallucinated candidates could influence claim
   120	synthesis before the human acceptance step meant to catch that. The chain is: this feature
   121	produces Candidate Evidence → EA-0008 (Knowledge Review) produces Accepted Evidence →
   122	EA-0006 (Claim Construction) consumes Accepted Evidence. EA-0006's dependency on this
   123	feature's output is indirect, mediated through EA-0008's acceptance decision, not a direct
   124	dependency on Candidate Evidence itself.
   125	
   126	Downstream (soft): EA-0005 (Ambiguity Construction) is the deliberate exception to the
   127	correction above — its pre-claim path explicitly accepts manually-referred Candidate
   128	Evidence pairs directly from this feature, without requiring EA-0008's acceptance first,
   129	since that path is explicitly analytical/provisional (it can conclude "no real conflict" or
   130	"insufficient context") and doesn't promote those candidates into the accepted evidence
   131	base. Not a hard dependency in the sense of being required for this feature to run, but
   132	worth keeping in mind, since `initiate.md`'s original contradiction-handling flow only
   133	considered ambiguity emerging at the claim level.
   134	
   135	## Rough Scope Notes
   136	
   137	In scope (rough): locating candidate passages relevant to the approved Research Questions,
   138	within the approved Research Corpus only; capturing exact excerpts with resolvable
   139	provenance and sufficient context; producing a bounded interpretation per passage plus a
   140	short selection rationale explaining why it belongs to the investigation; linking each
   141	candidate evidence item to one or more Research Questions; running the narrow structural/
   142	grounding preflight checks listed above; explicitly reporting when no candidate evidence is
   143	found for a Research Question; recognizing mechanical duplication while preserving
   144	corroboration signal; emitting results as provisional Candidate Evidence pending
   145	acceptance.
   146	
   147	Out of scope (rough): any new source discovery, web search, or crawling (stays inside
   148	EA-0003's boundary); the substantive acceptance decision (accept/reject/revise — belongs to
   149	EA-0008, Knowledge Review); contradiction or ambiguity reasoning; claim
   150	construction; reasoning about what corroboration *means* or aggregating corroborating
   151	evidence (a later feature's job — this feature only preserves the distinction from
   152	duplication); canonical ownership of the "Evidence Category" vocabulary term (left
   153	intentionally open per EA-0002, for the same premature-ontology reason).
   154	
   155	## Readiness Check
   156	
   157	- [x] The problem statement explains WHY, not HOW
   158	- [x] The primary actor is a human role, not "the system"
   159	- [x] The core outcome is stated from the actor's perspective
   160	- [x] At least one open question is listed (seven listed)
   161	- [x] Suspected dependencies are named (even if marked uncertain)
   162	- [x] No actor+outcome DBA form appears anywhere in this brief
   163	- [x] No stable guarantees or DBA scope boundaries appear in this brief
   164	- [x] The feature can be described without mentioning implementation technology
   165	- [x] (R-type only) — n/a, this is F-type
   166	
   167	**Brief status**: READY FOR STAGE 1
   168	
   169	---
   170	
   171	<!-- METADATA -->
   172	brief_created: 2026-07-17
   173	brief_last_updated: 2026-07-18
   174	stage1_started:

codex
**Acceptance Criteria**

1. Problem clearly stated: satisfied. EA-0008 states the gap: no owner exists for checking whether evidence, claims, and ambiguities become trustworthy knowledge before entering the trusted base ([backlog/EA-0008-knowledge_review.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:14), [line 20](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:20)).

2. Scope explicitly bounded: satisfied. In-scope review activities are listed, and exclusions are explicit: no candidate production, no investigation/publication approval, no Policy Registry definition ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:84), [line 91](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:91)).

3. No implementation detail: satisfied. The brief describes roles, candidate artifacts, outcomes, dependencies, and policy consultation, but no implementation technology; the readiness check also asserts this ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:105)).

4. Ready to become Stage 1 Intent: satisfied. It has problem, actor, outcome, open questions, dependencies, informal scope, and marks “READY FOR STAGE 1” ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:95), [line 108](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:108)).

5. Value/risk/guardrail present: satisfied. Value/risk: prevents possibly hallucinated material from silently reaching publication ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:14)). Guardrails: review owns trust decisions but not producing candidates, investigation approval, publication approval, or the Policy Registry ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:86), [line 91](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:91)).

**Claim Support**

Strong claims are sufficiently supported for this stage. The unified “Knowledge Reviewer” role is backed by matching corrections in EA-0004, EA-0005, and EA-0006 ([EA-0004](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:23), [EA-0005](/home/rimo/projects/EvidenceAtlas/backlog/EA-0005-ambiguity_construction.md:23), [EA-0006](/home/rimo/projects/EvidenceAtlas/backlog/EA-0006-claim_construction.md:23)). The claim that EA-0008 consumes Candidate Evidence, constructed Ambiguities, and Candidate Claims is mirrored by those briefs’ dependency sections ([EA-0004](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:110), [EA-0005](/home/rimo/projects/EvidenceAtlas/backlog/EA-0005-ambiguity_construction.md:93), [EA-0006](/home/rimo/projects/EvidenceAtlas/backlog/EA-0006-claim_construction.md:89)). External references to AJ-003/discovery docs are not independently verifiable in the packet, but the brief records the Policy Registry dependency as a belief/not yet verified, so this does not create a blocker ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:68)).

**Scope Drift**

No scope drift found. The packet includes EA-0004/EA-0005/EA-0006 corrections, but EA-0008 explicitly claims those briefs are being corrected for role consolidation ([EA-0008](/home/rimo/projects/EvidenceAtlas/backlog/EA-0008-knowledge_review.md:24)), and the edits remain at brief/dependency alignment level rather than implementation or downstream doctrine enforcement.

**In-Scope Blockers**

No IN-SCOPE BLOCKER findings.

**Finding Classification**

No findings raised.

PR decision: ADVANCE  
Scope drift warning: no — related brief corrections are claimed by this artifact and stay within brief-stage alignment.

LOG SUMMARY: NO OBJECTION — EA-0008 satisfies brief-stage acceptance criteria with no in-scope blockers.
EVIDENCE: A
HIGHEST-IMPACT UNCERTAINTY: The packet does not include AJ-003 itself, so external architecture-journal support for the role/policy consolidation is accepted only as represented in these shown artifacts.
tokens used
23,970
