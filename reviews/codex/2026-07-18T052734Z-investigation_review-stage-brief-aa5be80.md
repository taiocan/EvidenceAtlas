---
review_id: REV__investigation_review__brief__R2
findings: []
unparsed_findings_count: 0
reviewed:
  feature: investigation_review
  stage: brief
  branch: main
  base_commit: (no base pin)
  review_commit: aa5be800de44b6dd7ac02a88eddb163baf5d85ff
  artifacts:
    - path: backlog/EA-0007-investigation_review.md
      sha256: 4325aa4b5f0b44b9b5769b8df928b93449c562d245b4f4de42064415e8f8e9b1
      visibility: shown
    - path: backlog/EA-0002-research_planning.md
      sha256: 16fce284f7dcfff261f2a1ee047befb460b4a72a9784c9f55f26e4c9ad9833e7
      visibility: shown
    - path: backlog/EA-0003-corpus_construction.md
      sha256: fd4739f84236baa2feb12ac3c74aa53958670986beb7445dac7bd221869d627f
      visibility: shown
  diff_hash: e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
  coverage_state: FULL_COVERAGE
  workspace_dirty: true
  redaction_count: 0
  secret_redaction: false
  excluded_paths: []
  reviewed_packet: packets/20260718T052734Z-investigation_review-stage-brief-aa5be80.packet.txt
  reviewed_packet_sha256: 2cc8c9b1ad8e663984a50ea957f32766c3e803f769f0204364a88c68f1a8d8b7
  reviewer: "codex (session 019f73ae-50b7-7cc2-bf18-30b4f6b47fe3)"
  codex_concern: NO OBJECTION
  effective_concern: NO OBJECTION
  evidence: B
  reasoning_effort: high
  reconnect_count: 0
  elapsed_ms: 93680
---

**Acceptance Criteria**
1. Problem clearly stated: satisfied. Evidence: [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:11) explains the missing investigation setup review and risk of wasted research.
2. Upgrade/value: satisfied. Evidence: [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:28) gives the Editor an approve/decline review point before evidence collection.
3. Bounded scope: satisfied. Evidence: [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:68) lists rough in-scope and out-of-scope boundaries.
4. Proposed artifact(s): satisfied. Evidence: [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:34) proposes an Investigation Approval record and defers exact shape to Stage 1/2.
5. Risk/guardrail: satisfied. Evidence: risk at [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:13); guardrail at [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:50).
6. No implementation detail / ready for Stage 1: satisfied. Evidence: [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:36) explicitly defers fields/storage; readiness is stated at [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:89) and [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:92).

**Claim Support**
Strong claims are sufficiently supported for this stage. EA-0007’s proposed blocking answer is supported by EA-0002’s resolved tension assigning investigation-setup gating to EA-0007 at [EA-0002](/home/rimo/projects/EvidenceAtlas/backlog/EA-0002-research_planning.md:45). EA-0003’s dependence on an approved Research Plan is supported at [EA-0003](/home/rimo/projects/EvidenceAtlas/backlog/EA-0003-corpus_construction.md:13) and [EA-0003](/home/rimo/projects/EvidenceAtlas/backlog/EA-0003-corpus_construction.md:85). AJ-003 itself is not shown, but the packet’s included briefs carry the relevant cross-reference; I do not treat the missing journal text as a blocker for a Stage 0/brief artifact.

**Scope Drift**
No scope drift found. The artifact stays at brief level, proposes rather than specifies the Investigation Approval record, and does not introduce implementation mechanics, schema, CI, hooks, autonomous approval, rollback, or binding enforcement.

**In-Scope Blockers**
No IN-SCOPE BLOCKER findings.

**Finding Classification**
No findings raised, so no triage category applies.

PR decision: ADVANCE  
Scope drift warning: no — the packet stays within brief-stage proposal and supporting brief context.  
LOG SUMMARY: NO OBJECTION — The brief satisfies the stated Stage Brief criteria without in-scope blockers.
EVIDENCE: B
HIGHEST-IMPACT UNCERTAINTY: Whether AJ-003 exactly matches the briefs’ attribution is the main unverified support point, but it does not change the brief-stage acceptance result.
OpenAI Codex v0.142.5
--------
workdir: /home/rimo/projects/EvidenceAtlas
model: gpt-5.5
provider: openai
approval: never
sandbox: read-only
reasoning effort: high
reasoning summaries: none
session id: 019f73ae-50b7-7cc2-bf18-30b4f6b47fe3
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
  generated: 2026-07-18T05:26:00Z
  task_prompt: /home/rimo/projects/Codeos/prompts/codeos-reviewer-task.md (4959 bytes)
  review_content_bytes: 17493
  estimated_review_tokens: ~4373
  budget_status: OK
  packet_mode: full
  delta_base: none
  items:
    - path: backlog/EA-0007-investigation_review.md
      mode: full_file
      bytes: 4852
      sha256: 4325aa4b5f0b44b9b5769b8df928b93449c562d245b4f4de42064415e8f8e9b1
    - path: backlog/EA-0002-research_planning.md
      mode: full_file
      bytes: 6285
      sha256: 16fce284f7dcfff261f2a1ee047befb460b4a72a9784c9f55f26e4c9ad9833e7
    - path: backlog/EA-0003-corpus_construction.md
      mode: full_file
      bytes: 6356
      sha256: fd4739f84236baa2feb12ac3c74aa53958670986beb7445dac7bd221869d627f
    - path: (diff)
      mode: full_file
      bytes: 0

REVIEW CONTEXT
  Feature:                investigation_review
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
  --- backlog/EA-0007-investigation_review.md (sha256: 4325aa4b5f0b44b9b5769b8df928b93449c562d245b4f4de42064415e8f8e9b1, visibility: shown) ---
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

  --- backlog/EA-0002-research_planning.md (sha256: 16fce284f7dcfff261f2a1ee047befb460b4a72a9784c9f55f26e4c9ad9833e7, visibility: shown) ---
    # Feature Brief: EA-0002 — Research Planning
    
    **Slug**: research_planning
    **Type**: F-type
    **Refines**: n/a
    **Tier**: 0 — Foundational (second domain feature; depends only on EA-0001)
    **Status**: BRIEF-DRAFT
    
    ---
    
    ## Problem / Need
    
    Without explicit research planning, an investigation has no explicit strategy: important
    perspectives get discovered accidentally, search coverage depends on whatever a search
    engine happens to surface, evidence gaps can't be recognized because nobody anticipated
    them, and two researchers handed the same Research Brief could end up investigating
    completely different things. The Research Brief defines the decision problem; nothing
    today defines what evidence must exist before that problem can be answered responsibly.
    
    ## Primary Actor
    
    The Editor / Research Lead — the same role from EA-0001. Here they review and approve the
    proposed investigation strategy (represented by the Research Plan) before any resources are
    spent collecting evidence. The actor is defined by who receives the value (confidence in
    the strategy before spending), not by who does the reasoning that produces the plan.
    
    ## Core Outcome (informal)
    
    The Editor can evaluate whether the proposed investigation is capable of answering the
    original decision question before committing resources to evidence collection. Success is
    not "the plan looks reasonable" — it's confidence that, if this plan is executed
    successfully, the resulting corpus *should* be sufficient to answer the decision question
    within the agreed scope and constraints. Planning never guarantees the outcome; it
    guarantees intentionality — that the investigation was designed on purpose rather than
    discovered by accident.
    
    ## Design Tensions and Open Questions
    
    1. Is Research Planning rule-driven (a fixed checklist of perspective types — academic,
       regulatory, vendor, critical) or question-driven (perspectives derived by reasoning
       about *this specific* decision question)? [Tentative: question-driven. A fixed taxonomy
       just relocates the ontology problem EA-0001 deliberately avoided one feature downstream —
       "should hospitals adopt federated learning" and "should AMD acquire Company X" need
       structurally different investigations, not the same checklist.]
    2. Should editor approval of the Research Plan be a hard blocking gate before Corpus
       Construction can start, or advisory? **[Resolved, 2026-07-18, per Architecture Journal
       AJ-003:** progress beyond the investigation-setup phase is blocked until Investigation
       Review (EA-0007) approves the required artifacts — this feature does not itself gate
       anything; the governance responsibility belongs entirely to EA-0007, which reviews the
       Research Brief and this feature's Research Plan together as one phase.]
    3. If the editor rejects a plan, is it revised in place, or does that produce a new version?
       [Tentative: new version — Plan v1 → Rejected → Plan v2, mirroring EA-0001's
       revision-not-edit pattern, so it stays possible to know which plan version produced
       which corpus.]
    4. Can Research Planning restart after Corpus Construction has already begun? [Tentative:
       only explicitly, never silently. A changed Decision Question produces Brief v2 → Plan v2
       → Corpus v2 — planning must never mutate under an executing corpus.]
    5. Should individual Research Questions carry a stable identifier so downstream evidence,
       claims, and eventual Decision Brief content can trace back to which question motivated
       collecting them, and ultimately back to the Decision Question itself? [Not required for
       this feature or for EA-0003 to function — flagged as a forward-looking design
       expectation later features will likely need, not a dependency this feature has today.]
    
    ## Suspected Dependencies
    
    Upstream: EA-0001 (Research Brief) only.
    
    Downstream (hard): EA-0003 (Corpus Construction) consumes the Research Plan's Perspectives,
    Coverage Goals, Stopping Criteria, and Research Questions directly — and normatively, not
    just structurally. The plan defines what "successfully executed" even means for EA-0003.
    
    Downstream (soft, traceability): not required for EA-0003 to function, but later features
    (Evidence Extraction, Claim Construction, an eventual Decision Brief) will likely want to
    trace a piece of evidence or claim back to the specific Research Question that motivated
    seeking it. This is a forward-looking design property worth keeping in mind, not a
    functional dependency this feature carries today.
    
    ## Rough Scope Notes
    
    In scope (rough): deriving Research Questions, required perspectives, and stopping criteria
    from an approved Research Brief; producing one reviewable Research Plan.
    
    Out of scope (rough): query execution or actual searching/retrieval (that's EA-0003);
    source ranking, retrieval optimization, search-query tuning, or cost optimization (all
    execution concerns); a fixed/hardcoded perspective-type taxonomy; plan versioning or
    comparison beyond a simple reject-and-revise cycle.
    
    **Note (intentionally undecided):** ownership of "Evidence Category" as a canonical
    vocabulary term is left open on purpose — it may belong to evidence modeling (a later,
    not-yet-briefed feature) rather than to Planning. Planning may reference categories without
    owning their canonical definition; forcing that decision now risks the same premature-
    ontology problem this brief is otherwise avoiding.
    
    ## Readiness Check
    
    - [x] The problem statement explains WHY, not HOW
    - [x] The primary actor is a human role, not "the system"
    - [x] The core outcome is stated from the actor's perspective
    - [x] At least one open question is listed (five listed)
    - [x] Suspected dependencies are named (even if marked uncertain)
    - [x] No actor+outcome DBA form appears anywhere in this brief
    - [x] No stable guarantees or DBA scope boundaries appear in this brief (the
          investigation-setup blocking rule is a cross-feature governance note owned by
          EA-0007, not a formal DBA contract stated by this feature)
    - [x] The feature can be described without mentioning implementation technology
    - [x] (R-type only) — n/a, this is F-type
    
    **Brief status**: READY FOR STAGE 1
    
    ---
    
    <!-- METADATA -->
    brief_created: 2026-07-17
    brief_last_updated: 2026-07-18
    stage1_started:

  --- backlog/EA-0003-corpus_construction.md (sha256: fd4739f84236baa2feb12ac3c74aa53958670986beb7445dac7bd221869d627f, visibility: shown) ---
    # Feature Brief: EA-0003 — Corpus Construction
    
    **Slug**: corpus_construction
    **Type**: F-type
    **Refines**: n/a
    **Tier**: 0 — Foundational (third domain feature; depends only on EA-0002)
    **Status**: BRIEF-DRAFT
    
    ---
    
    ## Problem / Need
    
    The problem is not finding sources — it's constructing a corpus that faithfully implements
    the approved Research Plan. Without this, sources get gathered, but nobody knows whether
    the required viewpoints were actually represented, duplicate evidence overwhelms unique
    evidence, coverage of the plan can't be assessed, and evidence quality varies
    unpredictably from one investigation to the next.
    
    ## Primary Actor
    
    The Editor / Research Lead — the same role as EA-0001/EA-0002. They need confidence that
    the collected corpus adequately represents the planned investigation before evidence
    extraction begins. They may not inspect every document, but they are the consumer of the
    resulting assessment of how the plan was actually executed.
    
    ## Core Outcome (informal)
    
    The Editor can understand how completely the approved investigation was executed, what
    evidence was successfully obtained, what remains missing, and why. The value isn't "I have
    a corpus" — nobody wants a corpus for its own sake — it's "I understand whether this corpus
    is an adequate foundation for evidence extraction, including any known limitations that
    could materially affect downstream conclusions." Adequate deliberately does not mean
    complete.
    
    ## Design Tensions and Open Questions
    
    1. Is Corpus Construction optimizing for evidence quality or investigation completeness?
       [Resolved as a principle: optimize for plan fulfillment, and report quality
       characteristics rather than silently filtering required perspectives away. A mediocre
       but genuinely opposing source shouldn't be dropped on quality grounds if the plan
       required that perspective — quality becomes information attached to the corpus, not a
       silent filtering policy.]
    2. Should this feature notice contradictions between sources? [Resolved: no. It reports only
       structural properties — perspective found, perspective missing, source duplicated,
       retrieval failed. Judging that two studies actually contradict each other requires
       interpreting evidence, which belongs to a later, not-yet-briefed feature.]
    3. Does this feature ever decide an incomplete corpus is "acceptable"? [Resolved as a
       principle: never. It only determines whether the Plan has been satisfied as far as
       practical and reports the gaps. What happens next — block, proceed with documented gaps,
       or escalate to the editor — is deliberately deferred to a later feature or architectural
       decision, since different operating modes may legitimately want different behavior. This
       is also tracked under Architecture Journal AJ-001.]
    4. If the Research Brief is revised after corpus construction has started, does the corpus
       update incrementally or restart? [Resolved: restart — Brief v2 → Plan v2 → Corpus v2, no
       incremental mutation of a corpus already in progress, to keep provenance intact.]
    5. Within the resulting **Research Execution Report** (renamed from an earlier "Coverage
       Assessment" framing — coverage is only one dimension of whether execution actually
       succeeded), which information should stay execution-local versus travel downstream to
       later features? [Tentative split: *operational telemetry* — retrieval timestamps, retry
       counts, download failures, API errors — stays local to this feature. *Evidence-base
       characteristics* — missing planned perspectives, an unusually sparse corpus, a skewed
       quality distribution — should remain visible downstream, since they give later features
       context for confidence assessment without requiring this feature to interpret evidence
       itself. **One open nuance, not fully resolved:** "stopping reason" (e.g. "plan fully
       satisfied" vs. "ran out of budget" vs. "no further sources existed") carries real weight
       for how much to trust the corpus's completeness — closer to an evidence-base
       characteristic than to pure operational telemetry like a retry count. Recorded here as
       evidence-base-characteristic (downstream-visible) pending Stage 1/2 confirmation.]
    
    ## Suspected Dependencies
    
    Upstream: EA-0002 (Research Plan) only.
    
    Downstream (hard): the next, not-yet-briefed feature (Evidence Extraction) consumes both
    the Research Corpus and the Research Execution Report directly.
    
    Downstream (soft): Claim Construction and/or the Contradiction Resolution Workflow may want
    the Execution Report's evidence-base characteristics (missing perspectives, sparse
    coverage, quality distribution, stopping reason) as context for confidence assessment —
    without this feature making any interpretive judgment itself. Purely operational telemetry
    (retrieval duration, retry counts, raw error codes) shouldn't need to travel that far.
    
    ## Rough Scope Notes
    
    In scope (rough): discovering sources per the approved Plan; mechanical deduplication;
    structural coverage measurement against required perspectives; producing a Research Corpus
    plus a Research Execution Report (coverage assessment, retrieval outcomes, known gaps,
    quality signals, stopping reason, execution summary).
    
    Out of scope (rough): evidence interpretation, claim construction, or contradiction
    judgment (all later features); deduplication *policy* decisions beyond mechanical dedup;
    source credibility judgment beyond whatever objective quality signals are defined for
    assembly; deciding that a required perspective "doesn't matter anymore" — that's an
    interpretation, not an execution fact.
    
    ## Readiness Check
    
    - [x] The problem statement explains WHY, not HOW
    - [x] The primary actor is a human role, not "the system"
    - [x] The core outcome is stated from the actor's perspective
    - [x] At least one open question is listed (five listed)
    - [x] Suspected dependencies are named (even if marked uncertain)
    - [x] No actor+outcome DBA form appears anywhere in this brief
    - [x] No stable guarantees or DBA scope boundaries appear in this brief
    - [x] The feature can be described without mentioning implementation technology
    - [x] (R-type only) — n/a, this is F-type
    
    **Brief status**: READY FOR STAGE 1
    
    ---
    
    <!-- METADATA -->
    brief_created: 2026-07-17
    brief_last_updated: 2026-07-17
    stage1_started:

DIFF TO REVIEW (base->review, secret/size filtered)

codex
I’ll reassess from this new packet only. The added EA-0002/EA-0003 context changes the support picture, so I’m checking exact line anchors before classifying findings.
exec
/bin/bash -lc 'nl -ba backlog/EA-0003-corpus_construction.md' in /home/rimo/projects/EvidenceAtlas
 succeeded in 0ms:
     1	# Feature Brief: EA-0003 — Corpus Construction
     2	
     3	**Slug**: corpus_construction
     4	**Type**: F-type
     5	**Refines**: n/a
     6	**Tier**: 0 — Foundational (third domain feature; depends only on EA-0002)
     7	**Status**: BRIEF-DRAFT
     8	
     9	---
    10	
    11	## Problem / Need
    12	
    13	The problem is not finding sources — it's constructing a corpus that faithfully implements
    14	the approved Research Plan. Without this, sources get gathered, but nobody knows whether
    15	the required viewpoints were actually represented, duplicate evidence overwhelms unique
    16	evidence, coverage of the plan can't be assessed, and evidence quality varies
    17	unpredictably from one investigation to the next.
    18	
    19	## Primary Actor
    20	
    21	The Editor / Research Lead — the same role as EA-0001/EA-0002. They need confidence that
    22	the collected corpus adequately represents the planned investigation before evidence
    23	extraction begins. They may not inspect every document, but they are the consumer of the
    24	resulting assessment of how the plan was actually executed.
    25	
    26	## Core Outcome (informal)
    27	
    28	The Editor can understand how completely the approved investigation was executed, what
    29	evidence was successfully obtained, what remains missing, and why. The value isn't "I have
    30	a corpus" — nobody wants a corpus for its own sake — it's "I understand whether this corpus
    31	is an adequate foundation for evidence extraction, including any known limitations that
    32	could materially affect downstream conclusions." Adequate deliberately does not mean
    33	complete.
    34	
    35	## Design Tensions and Open Questions
    36	
    37	1. Is Corpus Construction optimizing for evidence quality or investigation completeness?
    38	   [Resolved as a principle: optimize for plan fulfillment, and report quality
    39	   characteristics rather than silently filtering required perspectives away. A mediocre
    40	   but genuinely opposing source shouldn't be dropped on quality grounds if the plan
    41	   required that perspective — quality becomes information attached to the corpus, not a
    42	   silent filtering policy.]
    43	2. Should this feature notice contradictions between sources? [Resolved: no. It reports only
    44	   structural properties — perspective found, perspective missing, source duplicated,
    45	   retrieval failed. Judging that two studies actually contradict each other requires
    46	   interpreting evidence, which belongs to a later, not-yet-briefed feature.]
    47	3. Does this feature ever decide an incomplete corpus is "acceptable"? [Resolved as a
    48	   principle: never. It only determines whether the Plan has been satisfied as far as
    49	   practical and reports the gaps. What happens next — block, proceed with documented gaps,
    50	   or escalate to the editor — is deliberately deferred to a later feature or architectural
    51	   decision, since different operating modes may legitimately want different behavior. This
    52	   is also tracked under Architecture Journal AJ-001.]
    53	4. If the Research Brief is revised after corpus construction has started, does the corpus
    54	   update incrementally or restart? [Resolved: restart — Brief v2 → Plan v2 → Corpus v2, no
    55	   incremental mutation of a corpus already in progress, to keep provenance intact.]
    56	5. Within the resulting **Research Execution Report** (renamed from an earlier "Coverage
    57	   Assessment" framing — coverage is only one dimension of whether execution actually
    58	   succeeded), which information should stay execution-local versus travel downstream to
    59	   later features? [Tentative split: *operational telemetry* — retrieval timestamps, retry
    60	   counts, download failures, API errors — stays local to this feature. *Evidence-base
    61	   characteristics* — missing planned perspectives, an unusually sparse corpus, a skewed
    62	   quality distribution — should remain visible downstream, since they give later features
    63	   context for confidence assessment without requiring this feature to interpret evidence
    64	   itself. **One open nuance, not fully resolved:** "stopping reason" (e.g. "plan fully
    65	   satisfied" vs. "ran out of budget" vs. "no further sources existed") carries real weight
    66	   for how much to trust the corpus's completeness — closer to an evidence-base
    67	   characteristic than to pure operational telemetry like a retry count. Recorded here as
    68	   evidence-base-characteristic (downstream-visible) pending Stage 1/2 confirmation.]
    69	
    70	## Suspected Dependencies
    71	
    72	Upstream: EA-0002 (Research Plan) only.
    73	
    74	Downstream (hard): the next, not-yet-briefed feature (Evidence Extraction) consumes both
    75	the Research Corpus and the Research Execution Report directly.
    76	
    77	Downstream (soft): Claim Construction and/or the Contradiction Resolution Workflow may want
    78	the Execution Report's evidence-base characteristics (missing perspectives, sparse
    79	coverage, quality distribution, stopping reason) as context for confidence assessment —
    80	without this feature making any interpretive judgment itself. Purely operational telemetry
    81	(retrieval duration, retry counts, raw error codes) shouldn't need to travel that far.
    82	
    83	## Rough Scope Notes
    84	
    85	In scope (rough): discovering sources per the approved Plan; mechanical deduplication;
    86	structural coverage measurement against required perspectives; producing a Research Corpus
    87	plus a Research Execution Report (coverage assessment, retrieval outcomes, known gaps,
    88	quality signals, stopping reason, execution summary).
    89	
    90	Out of scope (rough): evidence interpretation, claim construction, or contradiction
    91	judgment (all later features); deduplication *policy* decisions beyond mechanical dedup;
    92	source credibility judgment beyond whatever objective quality signals are defined for
    93	assembly; deciding that a required perspective "doesn't matter anymore" — that's an
    94	interpretation, not an execution fact.
    95	
    96	## Readiness Check
    97	
    98	- [x] The problem statement explains WHY, not HOW
    99	- [x] The primary actor is a human role, not "the system"
   100	- [x] The core outcome is stated from the actor's perspective
   101	- [x] At least one open question is listed (five listed)
   102	- [x] Suspected dependencies are named (even if marked uncertain)
   103	- [x] No actor+outcome DBA form appears anywhere in this brief
   104	- [x] No stable guarantees or DBA scope boundaries appear in this brief
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
/bin/bash -lc 'nl -ba backlog/EA-0002-research_planning.md' in /home/rimo/projects/EvidenceAtlas
 succeeded in 0ms:
     1	# Feature Brief: EA-0002 — Research Planning
     2	
     3	**Slug**: research_planning
     4	**Type**: F-type
     5	**Refines**: n/a
     6	**Tier**: 0 — Foundational (second domain feature; depends only on EA-0001)
     7	**Status**: BRIEF-DRAFT
     8	
     9	---
    10	
    11	## Problem / Need
    12	
    13	Without explicit research planning, an investigation has no explicit strategy: important
    14	perspectives get discovered accidentally, search coverage depends on whatever a search
    15	engine happens to surface, evidence gaps can't be recognized because nobody anticipated
    16	them, and two researchers handed the same Research Brief could end up investigating
    17	completely different things. The Research Brief defines the decision problem; nothing
    18	today defines what evidence must exist before that problem can be answered responsibly.
    19	
    20	## Primary Actor
    21	
    22	The Editor / Research Lead — the same role from EA-0001. Here they review and approve the
    23	proposed investigation strategy (represented by the Research Plan) before any resources are
    24	spent collecting evidence. The actor is defined by who receives the value (confidence in
    25	the strategy before spending), not by who does the reasoning that produces the plan.
    26	
    27	## Core Outcome (informal)
    28	
    29	The Editor can evaluate whether the proposed investigation is capable of answering the
    30	original decision question before committing resources to evidence collection. Success is
    31	not "the plan looks reasonable" — it's confidence that, if this plan is executed
    32	successfully, the resulting corpus *should* be sufficient to answer the decision question
    33	within the agreed scope and constraints. Planning never guarantees the outcome; it
    34	guarantees intentionality — that the investigation was designed on purpose rather than
    35	discovered by accident.
    36	
    37	## Design Tensions and Open Questions
    38	
    39	1. Is Research Planning rule-driven (a fixed checklist of perspective types — academic,
    40	   regulatory, vendor, critical) or question-driven (perspectives derived by reasoning
    41	   about *this specific* decision question)? [Tentative: question-driven. A fixed taxonomy
    42	   just relocates the ontology problem EA-0001 deliberately avoided one feature downstream —
    43	   "should hospitals adopt federated learning" and "should AMD acquire Company X" need
    44	   structurally different investigations, not the same checklist.]
    45	2. Should editor approval of the Research Plan be a hard blocking gate before Corpus
    46	   Construction can start, or advisory? **[Resolved, 2026-07-18, per Architecture Journal
    47	   AJ-003:** progress beyond the investigation-setup phase is blocked until Investigation
    48	   Review (EA-0007) approves the required artifacts — this feature does not itself gate
    49	   anything; the governance responsibility belongs entirely to EA-0007, which reviews the
    50	   Research Brief and this feature's Research Plan together as one phase.]
    51	3. If the editor rejects a plan, is it revised in place, or does that produce a new version?
    52	   [Tentative: new version — Plan v1 → Rejected → Plan v2, mirroring EA-0001's
    53	   revision-not-edit pattern, so it stays possible to know which plan version produced
    54	   which corpus.]
    55	4. Can Research Planning restart after Corpus Construction has already begun? [Tentative:
    56	   only explicitly, never silently. A changed Decision Question produces Brief v2 → Plan v2
    57	   → Corpus v2 — planning must never mutate under an executing corpus.]
    58	5. Should individual Research Questions carry a stable identifier so downstream evidence,
    59	   claims, and eventual Decision Brief content can trace back to which question motivated
    60	   collecting them, and ultimately back to the Decision Question itself? [Not required for
    61	   this feature or for EA-0003 to function — flagged as a forward-looking design
    62	   expectation later features will likely need, not a dependency this feature has today.]
    63	
    64	## Suspected Dependencies
    65	
    66	Upstream: EA-0001 (Research Brief) only.
    67	
    68	Downstream (hard): EA-0003 (Corpus Construction) consumes the Research Plan's Perspectives,
    69	Coverage Goals, Stopping Criteria, and Research Questions directly — and normatively, not
    70	just structurally. The plan defines what "successfully executed" even means for EA-0003.
    71	
    72	Downstream (soft, traceability): not required for EA-0003 to function, but later features
    73	(Evidence Extraction, Claim Construction, an eventual Decision Brief) will likely want to
    74	trace a piece of evidence or claim back to the specific Research Question that motivated
    75	seeking it. This is a forward-looking design property worth keeping in mind, not a
    76	functional dependency this feature carries today.
    77	
    78	## Rough Scope Notes
    79	
    80	In scope (rough): deriving Research Questions, required perspectives, and stopping criteria
    81	from an approved Research Brief; producing one reviewable Research Plan.
    82	
    83	Out of scope (rough): query execution or actual searching/retrieval (that's EA-0003);
    84	source ranking, retrieval optimization, search-query tuning, or cost optimization (all
    85	execution concerns); a fixed/hardcoded perspective-type taxonomy; plan versioning or
    86	comparison beyond a simple reject-and-revise cycle.
    87	
    88	**Note (intentionally undecided):** ownership of "Evidence Category" as a canonical
    89	vocabulary term is left open on purpose — it may belong to evidence modeling (a later,
    90	not-yet-briefed feature) rather than to Planning. Planning may reference categories without
    91	owning their canonical definition; forcing that decision now risks the same premature-
    92	ontology problem this brief is otherwise avoiding.
    93	
    94	## Readiness Check
    95	
    96	- [x] The problem statement explains WHY, not HOW
    97	- [x] The primary actor is a human role, not "the system"
    98	- [x] The core outcome is stated from the actor's perspective
    99	- [x] At least one open question is listed (five listed)
   100	- [x] Suspected dependencies are named (even if marked uncertain)
   101	- [x] No actor+outcome DBA form appears anywhere in this brief
   102	- [x] No stable guarantees or DBA scope boundaries appear in this brief (the
   103	      investigation-setup blocking rule is a cross-feature governance note owned by
   104	      EA-0007, not a formal DBA contract stated by this feature)
   105	- [x] The feature can be described without mentioning implementation technology
   106	- [x] (R-type only) — n/a, this is F-type
   107	
   108	**Brief status**: READY FOR STAGE 1
   109	
   110	---
   111	
   112	<!-- METADATA -->
   113	brief_created: 2026-07-17
   114	brief_last_updated: 2026-07-18
   115	stage1_started:

exec
/bin/bash -lc 'nl -ba backlog/EA-0007-investigation_review.md' in /home/rimo/projects/EvidenceAtlas
 succeeded in 0ms:
     1	# Feature Brief: EA-0007 — Investigation Review
     2	
     3	**Slug**: investigation_review
     4	**Type**: F-type
     5	**Refines**: n/a
     6	**Tier**: 0 — Foundational (governance feature; consumes EA-0001 and EA-0002 directly)
     7	**Status**: BRIEF-DRAFT
     8	
     9	---
    10	
    11	## Problem / Need
    12	
    13	Without a review point for the investigation setup, resources could be spent researching a
    14	poorly-scoped or drifting investigation before any human confirms the Research Brief and
    15	the Research Plan derived from it are actually sound together. The revision discipline
    16	already established in EA-0001 and EA-0002 (Plan v1 → Rejected → Plan v2) has no review
    17	activity attached to it without this feature — it describes what versioning looks like, not
    18	who decides a version needs to happen.
    19	
    20	## Primary Actor
    21	
    22	The **Editor / Research Lead** — the same role already established in EA-0001 and EA-0002,
    23	not a new name. This feature formalizes the review activity those two briefs already
    24	assumed that actor performs.
    25	
    26	## Core Outcome (informal)
    27	
    28	The Editor can approve — or decline — the investigation setup (the Research Brief and its
    29	derived Research Plan together) before any resources are spent on evidence collection. This
    30	is one governance phase, not one atomic decision: the Editor can approve the Brief while
    31	separately sending the Plan back for revision, without needing to re-litigate the Brief
    32	itself.
    33	
    34	**Proposed artifact:** an Investigation Approval record — the outcome of one review pass,
    35	naming which of the Research Brief and Research Plan were approved, which (if any) were
    36	sent back for revision, and by whom. Exact shape (fields, storage) is Stage 1/2 work; this
    37	brief only proposes that such a record is this feature's output.
    38	
    39	## Design Tensions and Open Questions
    40	
    41	1. **What are the actual possible outcomes of one review pass?** [Tentative: (a) both
    42	   approved → Corpus Construction may begin; (b) Brief approved, Plan needs revision → a
    43	   new Plan version is produced and only that portion is re-reviewed; (c) Brief itself needs
    44	   revision.]
    45	2. **If the Brief changes, does the existing Plan survive?** [Tentative: no — a revised
    46	   Decision Question most likely invalidates a Plan derived from the old one, so a Brief
    47	   revision probably triggers Plan re-derivation and a fresh review of both. Not fully
    48	   resolved; a minor Brief clarification might not always require this, but treating it as
    49	   "probably yes" is the safer default until evidence says otherwise.]
    50	3. **Blocking, not advisory.** [Resolved as this brief's proposed answer to EA-0002's
    51	   previously open Design Tension #2 — see the corresponding correction note added there.
    52	   Because Plan approval is proposed as part of Investigation Review rather than a
    53	   standalone checkpoint, it is naturally blocking: Corpus Construction is not intended to
    54	   begin until this feature approves, at minimum, the Plan.]
    55	4. **Does every revision require full re-review, or just the changed artifact?** [Tentative:
    56	   just the changed artifact — a Plan v2 triggered by a plan-only rejection likely only
    57	   needs the Plan re-reviewed, not the already-approved Brief; a Brief v2 likely requires
    58	   review of both, per open question #2 above.]
    59	
    60	## Suspected Dependencies
    61	
    62	Upstream (hard): EA-0001 (Research Brief) and EA-0002 (Research Plan), both consumed
    63	directly and reviewed together as one phase.
    64	
    65	Downstream (hard): EA-0003 (Corpus Construction) does not begin until this feature approves
    66	the investigation, at minimum the Plan portion.
    67	
    68	## Rough Scope Notes
    69	
    70	In scope (rough): reviewing the Research Brief and Research Plan together as one governance
    71	phase; supporting partial approval/rejection outcomes; determining whether a Brief revision
    72	requires re-deriving and re-reviewing the Plan.
    73	
    74	Out of scope (rough): deriving the Plan itself (EA-0002's job); any evidence, claim, or
    75	ambiguity review (Knowledge Review's job, EA-0008); corpus-execution decisions, including
    76	the corpus-gap escalation (EA-0003's own exception path, explicitly excluded from this
    77	feature's scope per Architecture Journal AJ-003).
    78	
    79	## Readiness Check
    80	
    81	- [x] The problem statement explains WHY, not HOW
    82	- [x] The primary actor is a human role, not "the system"
    83	- [x] The core outcome is stated from the actor's perspective
    84	- [x] At least one open question is listed (four listed)
    85	- [x] Suspected dependencies are named (even if marked uncertain)
    86	- [x] No actor+outcome DBA form appears anywhere in this brief
    87	- [x] No stable guarantees or DBA scope boundaries appear in this brief (scope notes are
    88	      informal guardrails, not formal DBA contract language)
    89	- [x] The feature can be described without mentioning implementation technology
    90	- [x] (R-type only) — n/a, this is F-type
    91	
    92	**Brief status**: READY FOR STAGE 1
    93	
    94	---
    95	
    96	<!-- METADATA -->
    97	brief_created: 2026-07-17
    98	brief_last_updated: 2026-07-18
    99	stage1_started:

codex
**Acceptance Criteria**
1. Problem clearly stated: satisfied. Evidence: [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:11) explains the missing investigation setup review and risk of wasted research.
2. Upgrade/value: satisfied. Evidence: [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:28) gives the Editor an approve/decline review point before evidence collection.
3. Bounded scope: satisfied. Evidence: [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:68) lists rough in-scope and out-of-scope boundaries.
4. Proposed artifact(s): satisfied. Evidence: [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:34) proposes an Investigation Approval record and defers exact shape to Stage 1/2.
5. Risk/guardrail: satisfied. Evidence: risk at [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:13); guardrail at [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:50).
6. No implementation detail / ready for Stage 1: satisfied. Evidence: [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:36) explicitly defers fields/storage; readiness is stated at [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:89) and [EA-0007](/home/rimo/projects/EvidenceAtlas/backlog/EA-0007-investigation_review.md:92).

**Claim Support**
Strong claims are sufficiently supported for this stage. EA-0007’s proposed blocking answer is supported by EA-0002’s resolved tension assigning investigation-setup gating to EA-0007 at [EA-0002](/home/rimo/projects/EvidenceAtlas/backlog/EA-0002-research_planning.md:45). EA-0003’s dependence on an approved Research Plan is supported at [EA-0003](/home/rimo/projects/EvidenceAtlas/backlog/EA-0003-corpus_construction.md:13) and [EA-0003](/home/rimo/projects/EvidenceAtlas/backlog/EA-0003-corpus_construction.md:85). AJ-003 itself is not shown, but the packet’s included briefs carry the relevant cross-reference; I do not treat the missing journal text as a blocker for a Stage 0/brief artifact.

**Scope Drift**
No scope drift found. The artifact stays at brief level, proposes rather than specifies the Investigation Approval record, and does not introduce implementation mechanics, schema, CI, hooks, autonomous approval, rollback, or binding enforcement.

**In-Scope Blockers**
No IN-SCOPE BLOCKER findings.

**Finding Classification**
No findings raised, so no triage category applies.

PR decision: ADVANCE  
Scope drift warning: no — the packet stays within brief-stage proposal and supporting brief context.  
LOG SUMMARY: NO OBJECTION — The brief satisfies the stated Stage Brief criteria without in-scope blockers.
EVIDENCE: B
HIGHEST-IMPACT UNCERTAINTY: Whether AJ-003 exactly matches the briefs’ attribution is the main unverified support point, but it does not change the brief-stage acceptance result.
tokens used
27,794
