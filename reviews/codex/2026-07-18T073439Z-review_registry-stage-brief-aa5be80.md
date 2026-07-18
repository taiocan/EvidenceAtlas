---
review_id: REV__review_registry__brief__R2
findings: []
unparsed_findings_count: 0
reviewed:
  feature: review_registry
  stage: brief
  branch: main
  base_commit: (no base pin)
  review_commit: aa5be800de44b6dd7ac02a88eddb163baf5d85ff
  artifacts:
    - path: backlog/EA-0011-review_registry.md
      sha256: 5178ff667c239ee66efa3ad4666ff136a12128be35fda20c88fef20337647027
      visibility: shown
    - path: backlog/EA-0007-investigation_review.md
      sha256: 4325aa4b5f0b44b9b5769b8df928b93449c562d245b4f4de42064415e8f8e9b1
      visibility: shown
    - path: backlog/EA-0008-knowledge_review.md
      sha256: fdd794cfb039152c5db156acddd38cf03a5f0d6e2dccbff1b5e0e5b5b76bb790
      visibility: shown
    - path: backlog/EA-0009-publication_review.md
      sha256: 8289010488f97119d5b644fbe007fe94dfa0627c570c339d453ca0241dd0636e
      visibility: shown
    - path: backlog/EA-0010-policy_registry.md
      sha256: b10502415adb6ed11139915b750b19092d3595f1cf05f73937ac7f027b060e29
      visibility: shown
  diff_hash: e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
  coverage_state: FULL_COVERAGE
  workspace_dirty: true
  redaction_count: 0
  secret_redaction: false
  excluded_paths: []
  reviewed_packet: packets/20260718T073439Z-review_registry-stage-brief-aa5be80.packet.txt
  reviewed_packet_sha256: 5d17e4adcb3dd259318a0e13b087c437b6b75edb79c65320f3a2dc412cd1c218
  reviewer: "codex (session 019f7422-75c4-7d90-bb6d-63c8ba73f4c7)"
  codex_concern: NO OBJECTION
  effective_concern: NO OBJECTION
  evidence: A
  reasoning_effort: high
  reconnect_count: 0
  elapsed_ms: 58438
---

**Acceptance Criteria**
The artifact satisfies the brief-stage acceptance criteria.

Problem is clearly stated at `backlog/EA-0011-review_registry.md:17`: governance decisions exist across EA-0007/0008/0009 but require manual merging without a registry. The actor and outcome are human-centered at `EA-0011:26` and `EA-0011:33`. Scope is bounded at `EA-0011:75` and `EA-0011:79`, with unresolved boundaries left for Stage 1/2 at `EA-0011:48` and `EA-0011:55`. The proposed artifact is an append-only, queryable review ledger at `EA-0011:75`. Value/risk/guardrail are present through the audit-history value at `EA-0011:33`, open questions at `EA-0011:48-59`, and the no-authoring guardrail at `EA-0011:41` and `EA-0011:79`. No implementation technology is introduced, and the checklist explicitly says this remains a Stage 1/2 design principle rather than an approved DBA guarantee at `EA-0011:93`.

**Claim Support**
Strong claims are supported within the packet. EA-0011 claims the three source features produce canonical records at `EA-0011:17` and `EA-0011:63`; that is supported by EA-0007’s Investigation Approval record at `backlog/EA-0007-investigation_review.md:34`, EA-0008’s Knowledge Review record at `backlog/EA-0008-knowledge_review.md:43`, and EA-0009’s Publication Review record at `backlog/EA-0009-publication_review.md:37`. The “never edited”/append-only language at `EA-0011:44` is framed as a proposed design principle for Stage 1/2, not an implemented or approved guarantee, at `EA-0011:93`.

**Scope Drift**
No scope drift found. The additional EA-0008 and EA-0009 record-artifact statements directly support EA-0011’s source-record premise; no unrelated downstream doctrine modification is evident from the packet.

**In-Scope Blockers**
No IN-SCOPE BLOCKER findings.

PR decision: ADVANCE  
Scope drift warning: no — nothing in the packet pulls the PR beyond the review-registry brief’s stated scope.

LOG SUMMARY: NO OBJECTION — EA-0011 satisfies the brief-stage criteria with supported canonical source records
EVIDENCE: A
HIGHEST-IMPACT UNCERTAINTY: The packet notes uncommitted workspace changes, so the main uncertainty is whether these full-file contents exactly represent the intended review state.
OpenAI Codex v0.142.5
--------
workdir: /home/rimo/projects/EvidenceAtlas
model: gpt-5.5
provider: openai
approval: never
sandbox: read-only
reasoning effort: high
reasoning summaries: none
session id: 019f7422-75c4-7d90-bb6d-63c8ba73f4c7
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
  generated: 2026-07-18T07:33:40Z
  task_prompt: /home/rimo/projects/Codeos/prompts/codeos-reviewer-task.md (4959 bytes)
  review_content_bytes: 29064
  estimated_review_tokens: ~7266
  budget_status: OK
  packet_mode: full
  delta_base: none
  items:
    - path: backlog/EA-0011-review_registry.md
      mode: full_file
      bytes: 5505
      sha256: 5178ff667c239ee66efa3ad4666ff136a12128be35fda20c88fef20337647027
    - path: backlog/EA-0007-investigation_review.md
      mode: full_file
      bytes: 4852
      sha256: 4325aa4b5f0b44b9b5769b8df928b93449c562d245b4f4de42064415e8f8e9b1
    - path: backlog/EA-0008-knowledge_review.md
      mode: full_file
      bytes: 6641
      sha256: fdd794cfb039152c5db156acddd38cf03a5f0d6e2dccbff1b5e0e5b5b76bb790
    - path: backlog/EA-0009-publication_review.md
      mode: full_file
      bytes: 5481
      sha256: 8289010488f97119d5b644fbe007fe94dfa0627c570c339d453ca0241dd0636e
    - path: backlog/EA-0010-policy_registry.md
      mode: full_file
      bytes: 6585
      sha256: b10502415adb6ed11139915b750b19092d3595f1cf05f73937ac7f027b060e29
    - path: (diff)
      mode: full_file
      bytes: 0

REVIEW CONTEXT
  Feature:                review_registry
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
  --- backlog/EA-0011-review_registry.md (sha256: 5178ff667c239ee66efa3ad4666ff136a12128be35fda20c88fef20337647027, visibility: shown) ---
    # Feature Brief: EA-0011 — Review Registry
    
    **Slug**: review_registry
    **Type**: F-type
    **Refines**: n/a
    **Tier**: 0 — Foundational, third member of the shared infrastructure layer beneath the
    pipeline. Per Architecture Journal AJ-006, this is a **Derived Ledger** — a distinct
    sub-class from Policy Registry's **Authority** role and Dependency Registry's **Index**
    role. It authors nothing itself; it aggregates records the governance features already
    produce.
    **Status**: BRIEF-DRAFT
    
    ---
    
    ## Problem / Need
    
    EA-0007, EA-0008, and EA-0009 each make governance decisions and each will produce their
    own canonical record of those decisions — but without a unified place to look, answering a
    question like "what review history exists for this investigation" or "who approved this
    Claim, and when" requires separately querying three different places and manually merging
    the results by correlation. That's exactly the audit-trail gap `initiate.md` originally
    named this registry to close.
    
    ## Primary Actor
    
    The **Editor / Research Lead** — not as an author of review records (those are owned
    exclusively by EA-0007/EA-0008/EA-0009), but as the person who needs to reconstruct
    governance history: what was decided, by what rationale, and when, across an investigation
    or across the whole knowledge base.
    
    ## Core Outcome (informal)
    
    The Editor can look in one place to answer "what review decisions exist, in what order,
    with what rationale" for a given investigation, artifact, or reviewer — without needing to
    separately query Investigation Review, Knowledge Review, and Publication Review and merge
    the results by hand. This feature adds no new judgment of its own; it only makes existing
    judgments visible together.
    
    ## Design Tensions and Open Questions
    
    1. **This is a Derived Ledger, not an authoring feature.** [Resolved, per AJ-006: EA-0007,
       EA-0008, and EA-0009 each own authoring their own canonical decision record. This
       feature introduces no new authoring workflow and no business logic — it aggregates.]
    2. **Immutability.** [Resolved: entries in this ledger are never edited, only appended to.
       A correction is a new entry referencing the old one, never a rewrite — the same
       append-only Decision Log discipline already established in `dba-system.md`, and the same
       pattern this project's own `reviews/review-log.md` has used all session.]
    3. **Does Policy Registry's (EA-0010) change history belong in this same ledger, or stay
       separate?** [Not resolved. EA-0010 said policy changes are "versioned and auditable" but
       never specified where that history lives. Policy edits aren't quite the same kind of
       thing as an Investigation/Knowledge/Publication Review decision — they're operational
       configuration changes, not epistemic governance calls — so unifying them here isn't
       obviously right, but keeping two separate audit trails isn't obviously right either.
       Left for Stage 1/2.]
    4. **Does EA-0003's corpus-gap escalation belong here?** [Not resolved. AJ-003 explicitly
       excluded that decision from the governance-checkpoint count (it's operational exception
       handling, not a trust judgment) — but when a human does make that call, should it still
       be logged in this ledger for audit purposes, or does it fall outside this registry's
       scope entirely since it isn't one of the three AJ-003 governance classes? Left open.]
    
    ## Suspected Dependencies
    
    Upstream (hard): EA-0007 (Investigation Approval records), EA-0008 (Knowledge Review
    records), EA-0009 (Publication Review records) — all three are canonical sources this
    feature aggregates, not derives independently.
    
    Downstream (soft): the Editor/Research Lead, for reconstructing governance history; possibly
    a future audit or compliance-facing view, not yet needed for v1.
    
    Related, not yet resolved (see Design Tensions #3-4): EA-0010 (Policy Registry)'s change
    history, and EA-0003's corpus-gap escalation.
    
    ## Rough Scope Notes
    
    In scope (rough): aggregating the canonical review records from EA-0007/EA-0008/EA-0009
    into one append-only, queryable ledger; supporting queries by investigation, artifact, or
    reviewer; preserving full history with no edits to existing entries.
    
    Out of scope (rough): authoring or making any review decision itself (exclusively owned by
    the three governance features); any business logic beyond aggregation and querying; the
    canonical event log for state changes generally (a broader concern for the not-yet-briefed
    Change Event Registry to resolve against this one, per Architecture Journal AJ-006).
    
    ## Readiness Check
    
    - [x] The problem statement explains WHY, not HOW
    - [x] The primary actor is a human role, not "the system"
    - [x] The core outcome is stated from the actor's perspective
    - [x] At least one open question is listed (four listed; #1-2 resolved as principles, #3-4
          genuinely open)
    - [x] Suspected dependencies are named (even if marked uncertain)
    - [x] No actor+outcome DBA form appears anywhere in this brief
    - [x] No stable guarantees or DBA scope boundaries appear in this brief (the append-only/
          no-edit property in Design Tension #2 is a proposed design principle for Stage 1/2 to
          formalize, not an already-implemented or approved DBA guarantee)
    - [x] The feature can be described without mentioning implementation technology
    - [x] (R-type only) — n/a, this is F-type
    
    **Brief status**: READY FOR STAGE 1
    
    ---
    
    <!-- METADATA -->
    brief_created: 2026-07-18
    brief_last_updated: 2026-07-18
    stage1_started:

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

  --- backlog/EA-0008-knowledge_review.md (sha256: fdd794cfb039152c5db156acddd38cf03a5f0d6e2dccbff1b5e0e5b5b76bb790, visibility: shown) ---
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

  --- backlog/EA-0009-publication_review.md (sha256: 8289010488f97119d5b644fbe007fe94dfa0627c570c339d453ca0241dd0636e, visibility: shown) ---
    # Feature Brief: EA-0009 — Publication Review
    
    **Slug**: publication_review
    **Type**: F-type
    **Refines**: n/a
    **Tier**: 0 — Foundational (governance feature; depends on a not-yet-briefed Publishing
    feature and on EA-0008's accepted knowledge base)
    **Status**: BRIEF-DRAFT
    
    ---
    
    ## Problem / Need
    
    Without a final review before publishing, a published view could reach readers even if it
    misrepresents the underlying accepted knowledge — presenting a contested claim as settled
    fact, omitting a known ambiguity, or drifting from what was actually investigated. That
    would undermine the project's "decision support, not truth declaration" principle and the
    contested-claim-publication policy already hypothesized during Solution Discovery
    (`docs/solution-discovery-evidenceatlas.md` §7).
    
    ## Primary Actor
    
    The **Publication Reviewer** — a genuinely new role, distinct from the Knowledge Reviewer
    (EA-0008) and the Editor/Research Lead (EA-0007). The review question here is categorically
    different — "should this leave the system," an external-facing presentation judgment — not
    "can I trust this knowledge" or "is this the right investigation." Unlike Knowledge
    Review's actor consolidation, this isn't absorbing an existing name; it's a new judgment
    type with no prior equivalent in this pipeline.
    
    ## Core Outcome (informal)
    
    The Publication Reviewer can confirm that a proposed published view (Article, Reality
    Check, Decision Brief, or future Topic Page) accurately reflects the underlying accepted
    knowledge base — including any contested or ambiguous points and their required framing —
    before it becomes visible outside the system.
    
    **Proposed artifact:** a Publication Review record per decision — naming which published
    view was reviewed, the outcome (approved/returned for revision), and the rationale. Exact
    shape is Stage 1/2 work; this brief only proposes that such a record is this feature's
    output, one per decision made (added 2026-07-18, so EA-0011 (Review Registry) has a
    supported canonical source to aggregate).
    
    ## Design Tensions and Open Questions
    
    1. **Does this feature review content/framing decisions, or the final rendered artifact?**
       [Tentative: content and framing correctness — which claims and ambiguities were
       selected, how they're framed, whether required disclosures (e.g. showing opposing
       evidence for a contested claim) are present — not proofreading, formatting, or rendering,
       which belongs to the Presentation Layer.]
    2. **Policy-driven enforcement, not hardcoded rules.** [Tentative, consistent with EA-0007
       and EA-0008: this feature consults the not-yet-briefed Policy Registry for publication-
       time rules (e.g. the contested-claim-publication policy) rather than encoding them
       itself.]
    3. **Can this feature approve part of a multi-view output and reject another part?**
       [Not resolved — e.g. is the Reality Check sent back for revision while the Article is
       approved, or is it necessarily one judgment across the whole published package for a
       given investigation? Left open.]
    4. **Frequency.** [Tentative: once per published view, not once per investigation — since
       the not-yet-briefed Publishing feature is expected to produce multiple distinct views
       (Article, Reality Check, Decision Brief, Topic Page) from the same accepted claims, and
       each serves a different audience/purpose, so each plausibly needs independent review.]
    
    ## Suspected Dependencies
    
    Upstream (hard): a not-yet-briefed Publishing feature (produces draft published views from
    accepted Claims and Ambiguities) — a forward dependency, similar to how EA-0005 forward-
    referenced Claim Construction before it was briefed. Also EA-0008's accepted knowledge base
    (Accepted Evidence, Accepted Claims, structured Ambiguities), as the source of truth
    published views are checked against. Also a not-yet-briefed Policy Registry, consulted for
    publication-time policy enforcement.
    
    Downstream: none within this pipeline — this is the last internal checkpoint before
    external visibility. What comes after is publication itself, not another feature.
    
    ## Rough Scope Notes
    
    In scope (rough): confirming a published view's content and framing accurately reflect the
    accepted knowledge base, including required framing for contested or ambiguous points;
    consulting the Policy Registry for applicable publication-time policies.
    
    Out of scope (rough): generating the published view itself (the not-yet-briefed Publishing
    feature's job); proofreading, formatting, or rendering (Presentation Layer's job);
    re-litigating Knowledge Review's own accept/reject decisions, which are already settled by
    the time a view reaches this feature.
    
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

  --- backlog/EA-0010-policy_registry.md (sha256: b10502415adb6ed11139915b750b19092d3595f1cf05f73937ac7f027b060e29, visibility: shown) ---
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

DIFF TO REVIEW (base->review, secret/size filtered)

codex
I’ll reassess from this new packet only. The prior blocker about missing EA-0008/EA-0009 records has to be re-tested because this packet includes revised upstream briefs.
exec
/bin/bash -lc 'nl -ba backlog/EA-0011-review_registry.md' in /home/rimo/projects/EvidenceAtlas
exec
/bin/bash -lc 'nl -ba backlog/EA-0008-knowledge_review.md' in /home/rimo/projects/EvidenceAtlas
exec
/bin/bash -lc 'nl -ba backlog/EA-0009-publication_review.md' in /home/rimo/projects/EvidenceAtlas
 succeeded in 0ms:
     1	# Feature Brief: EA-0011 — Review Registry
     2	
     3	**Slug**: review_registry
     4	**Type**: F-type
     5	**Refines**: n/a
     6	**Tier**: 0 — Foundational, third member of the shared infrastructure layer beneath the
     7	pipeline. Per Architecture Journal AJ-006, this is a **Derived Ledger** — a distinct
     8	sub-class from Policy Registry's **Authority** role and Dependency Registry's **Index**
     9	role. It authors nothing itself; it aggregates records the governance features already
    10	produce.
    11	**Status**: BRIEF-DRAFT
    12	
    13	---
    14	
    15	## Problem / Need
    16	
    17	EA-0007, EA-0008, and EA-0009 each make governance decisions and each will produce their
    18	own canonical record of those decisions — but without a unified place to look, answering a
    19	question like "what review history exists for this investigation" or "who approved this
    20	Claim, and when" requires separately querying three different places and manually merging
    21	the results by correlation. That's exactly the audit-trail gap `initiate.md` originally
    22	named this registry to close.
    23	
    24	## Primary Actor
    25	
    26	The **Editor / Research Lead** — not as an author of review records (those are owned
    27	exclusively by EA-0007/EA-0008/EA-0009), but as the person who needs to reconstruct
    28	governance history: what was decided, by what rationale, and when, across an investigation
    29	or across the whole knowledge base.
    30	
    31	## Core Outcome (informal)
    32	
    33	The Editor can look in one place to answer "what review decisions exist, in what order,
    34	with what rationale" for a given investigation, artifact, or reviewer — without needing to
    35	separately query Investigation Review, Knowledge Review, and Publication Review and merge
    36	the results by hand. This feature adds no new judgment of its own; it only makes existing
    37	judgments visible together.
    38	
    39	## Design Tensions and Open Questions
    40	
    41	1. **This is a Derived Ledger, not an authoring feature.** [Resolved, per AJ-006: EA-0007,
    42	   EA-0008, and EA-0009 each own authoring their own canonical decision record. This
    43	   feature introduces no new authoring workflow and no business logic — it aggregates.]
    44	2. **Immutability.** [Resolved: entries in this ledger are never edited, only appended to.
    45	   A correction is a new entry referencing the old one, never a rewrite — the same
    46	   append-only Decision Log discipline already established in `dba-system.md`, and the same
    47	   pattern this project's own `reviews/review-log.md` has used all session.]
    48	3. **Does Policy Registry's (EA-0010) change history belong in this same ledger, or stay
    49	   separate?** [Not resolved. EA-0010 said policy changes are "versioned and auditable" but
    50	   never specified where that history lives. Policy edits aren't quite the same kind of
    51	   thing as an Investigation/Knowledge/Publication Review decision — they're operational
    52	   configuration changes, not epistemic governance calls — so unifying them here isn't
    53	   obviously right, but keeping two separate audit trails isn't obviously right either.
    54	   Left for Stage 1/2.]
    55	4. **Does EA-0003's corpus-gap escalation belong here?** [Not resolved. AJ-003 explicitly
    56	   excluded that decision from the governance-checkpoint count (it's operational exception
    57	   handling, not a trust judgment) — but when a human does make that call, should it still
    58	   be logged in this ledger for audit purposes, or does it fall outside this registry's
    59	   scope entirely since it isn't one of the three AJ-003 governance classes? Left open.]
    60	
    61	## Suspected Dependencies
    62	
    63	Upstream (hard): EA-0007 (Investigation Approval records), EA-0008 (Knowledge Review
    64	records), EA-0009 (Publication Review records) — all three are canonical sources this
    65	feature aggregates, not derives independently.
    66	
    67	Downstream (soft): the Editor/Research Lead, for reconstructing governance history; possibly
    68	a future audit or compliance-facing view, not yet needed for v1.
    69	
    70	Related, not yet resolved (see Design Tensions #3-4): EA-0010 (Policy Registry)'s change
    71	history, and EA-0003's corpus-gap escalation.
    72	
    73	## Rough Scope Notes
    74	
    75	In scope (rough): aggregating the canonical review records from EA-0007/EA-0008/EA-0009
    76	into one append-only, queryable ledger; supporting queries by investigation, artifact, or
    77	reviewer; preserving full history with no edits to existing entries.
    78	
    79	Out of scope (rough): authoring or making any review decision itself (exclusively owned by
    80	the three governance features); any business logic beyond aggregation and querying; the
    81	canonical event log for state changes generally (a broader concern for the not-yet-briefed
    82	Change Event Registry to resolve against this one, per Architecture Journal AJ-006).
    83	
    84	## Readiness Check
    85	
    86	- [x] The problem statement explains WHY, not HOW
    87	- [x] The primary actor is a human role, not "the system"
    88	- [x] The core outcome is stated from the actor's perspective
    89	- [x] At least one open question is listed (four listed; #1-2 resolved as principles, #3-4
    90	      genuinely open)
    91	- [x] Suspected dependencies are named (even if marked uncertain)
    92	- [x] No actor+outcome DBA form appears anywhere in this brief
    93	- [x] No stable guarantees or DBA scope boundaries appear in this brief (the append-only/
    94	      no-edit property in Design Tension #2 is a proposed design principle for Stage 1/2 to
    95	      formalize, not an already-implemented or approved DBA guarantee)
    96	- [x] The feature can be described without mentioning implementation technology
    97	- [x] (R-type only) — n/a, this is F-type
    98	
    99	**Brief status**: READY FOR STAGE 1
   100	
   101	---
   102	
   103	<!-- METADATA -->
   104	brief_created: 2026-07-18
   105	brief_last_updated: 2026-07-18
   106	stage1_started:

 succeeded in 0ms:
     1	# Feature Brief: EA-0009 — Publication Review
     2	
     3	**Slug**: publication_review
     4	**Type**: F-type
     5	**Refines**: n/a
     6	**Tier**: 0 — Foundational (governance feature; depends on a not-yet-briefed Publishing
     7	feature and on EA-0008's accepted knowledge base)
     8	**Status**: BRIEF-DRAFT
     9	
    10	---
    11	
    12	## Problem / Need
    13	
    14	Without a final review before publishing, a published view could reach readers even if it
    15	misrepresents the underlying accepted knowledge — presenting a contested claim as settled
    16	fact, omitting a known ambiguity, or drifting from what was actually investigated. That
    17	would undermine the project's "decision support, not truth declaration" principle and the
    18	contested-claim-publication policy already hypothesized during Solution Discovery
    19	(`docs/solution-discovery-evidenceatlas.md` §7).
    20	
    21	## Primary Actor
    22	
    23	The **Publication Reviewer** — a genuinely new role, distinct from the Knowledge Reviewer
    24	(EA-0008) and the Editor/Research Lead (EA-0007). The review question here is categorically
    25	different — "should this leave the system," an external-facing presentation judgment — not
    26	"can I trust this knowledge" or "is this the right investigation." Unlike Knowledge
    27	Review's actor consolidation, this isn't absorbing an existing name; it's a new judgment
    28	type with no prior equivalent in this pipeline.
    29	
    30	## Core Outcome (informal)
    31	
    32	The Publication Reviewer can confirm that a proposed published view (Article, Reality
    33	Check, Decision Brief, or future Topic Page) accurately reflects the underlying accepted
    34	knowledge base — including any contested or ambiguous points and their required framing —
    35	before it becomes visible outside the system.
    36	
    37	**Proposed artifact:** a Publication Review record per decision — naming which published
    38	view was reviewed, the outcome (approved/returned for revision), and the rationale. Exact
    39	shape is Stage 1/2 work; this brief only proposes that such a record is this feature's
    40	output, one per decision made (added 2026-07-18, so EA-0011 (Review Registry) has a
    41	supported canonical source to aggregate).
    42	
    43	## Design Tensions and Open Questions
    44	
    45	1. **Does this feature review content/framing decisions, or the final rendered artifact?**
    46	   [Tentative: content and framing correctness — which claims and ambiguities were
    47	   selected, how they're framed, whether required disclosures (e.g. showing opposing
    48	   evidence for a contested claim) are present — not proofreading, formatting, or rendering,
    49	   which belongs to the Presentation Layer.]
    50	2. **Policy-driven enforcement, not hardcoded rules.** [Tentative, consistent with EA-0007
    51	   and EA-0008: this feature consults the not-yet-briefed Policy Registry for publication-
    52	   time rules (e.g. the contested-claim-publication policy) rather than encoding them
    53	   itself.]
    54	3. **Can this feature approve part of a multi-view output and reject another part?**
    55	   [Not resolved — e.g. is the Reality Check sent back for revision while the Article is
    56	   approved, or is it necessarily one judgment across the whole published package for a
    57	   given investigation? Left open.]
    58	4. **Frequency.** [Tentative: once per published view, not once per investigation — since
    59	   the not-yet-briefed Publishing feature is expected to produce multiple distinct views
    60	   (Article, Reality Check, Decision Brief, Topic Page) from the same accepted claims, and
    61	   each serves a different audience/purpose, so each plausibly needs independent review.]
    62	
    63	## Suspected Dependencies
    64	
    65	Upstream (hard): a not-yet-briefed Publishing feature (produces draft published views from
    66	accepted Claims and Ambiguities) — a forward dependency, similar to how EA-0005 forward-
    67	referenced Claim Construction before it was briefed. Also EA-0008's accepted knowledge base
    68	(Accepted Evidence, Accepted Claims, structured Ambiguities), as the source of truth
    69	published views are checked against. Also a not-yet-briefed Policy Registry, consulted for
    70	publication-time policy enforcement.
    71	
    72	Downstream: none within this pipeline — this is the last internal checkpoint before
    73	external visibility. What comes after is publication itself, not another feature.
    74	
    75	## Rough Scope Notes
    76	
    77	In scope (rough): confirming a published view's content and framing accurately reflect the
    78	accepted knowledge base, including required framing for contested or ambiguous points;
    79	consulting the Policy Registry for applicable publication-time policies.
    80	
    81	Out of scope (rough): generating the published view itself (the not-yet-briefed Publishing
    82	feature's job); proofreading, formatting, or rendering (Presentation Layer's job);
    83	re-litigating Knowledge Review's own accept/reject decisions, which are already settled by
    84	the time a view reaches this feature.
    85	
    86	## Readiness Check
    87	
    88	- [x] The problem statement explains WHY, not HOW
    89	- [x] The primary actor is a human role, not "the system"
    90	- [x] The core outcome is stated from the actor's perspective
    91	- [x] At least one open question is listed (four listed)
    92	- [x] Suspected dependencies are named (even if marked uncertain)
    93	- [x] No actor+outcome DBA form appears anywhere in this brief
    94	- [x] No stable guarantees or DBA scope boundaries appear in this brief (scope notes are
    95	      informal guardrails, not formal DBA contract language)
    96	- [x] The feature can be described without mentioning implementation technology
    97	- [x] (R-type only) — n/a, this is F-type
    98	
    99	**Brief status**: READY FOR STAGE 1
   100	
   101	---
   102	
   103	<!-- METADATA -->
   104	brief_created: 2026-07-17
   105	brief_last_updated: 2026-07-18
   106	stage1_started:

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
    43	**Proposed artifact:** a Knowledge Review record per decision — naming which artifact was
    44	reviewed (Candidate Evidence, Candidate Claim, or Ambiguity), the outcome
    45	(accept/reject/return-for-revision), and the rationale. Exact shape is Stage 1/2 work; this
    46	brief only proposes that such a record is this feature's output, one per decision made
    47	(added 2026-07-18, so EA-0011 (Review Registry) has a supported canonical source to
    48	aggregate).
    49	
    50	## Design Tensions and Open Questions
    51	
    52	1. **This is recurring, not a single gate.** [Resolved, per Architecture Journal AJ-003:
    53	   this feature fires repeatedly — once evidence is extracted, once claims are synthesized,
    54	   once ambiguities are constructed — under one policy umbrella, rather than being one
    55	   checkpoint that happens once per investigation.]
    56	2. **Does this feature own the accept/reject/return-for-revision decisions previously
    57	   assumed by EA-0004 and EA-0006?** [Resolved: yes. This is where those "assumptions
    58	   requiring validation" become owned decisions — accept/reject/revise on Candidate
    59	   Evidence; accept/reject/revise on Candidate Claims; accept/return-for-more-analysis on
    60	   constructed Ambiguities. This feature also owns routing a human-initiated suspected-
    61	   disagreement referral to EA-0005 (previously described as something "Gate 1" did in
    62	   EA-0004's brief).]
    63	3. **Does review of one artifact type block progress on others?** [Not resolved — must all
    64	   evidence for a Research Question be accepted before Claim Construction can run on any of
    65	   it, or can synthesis proceed incrementally as evidence is accepted in batches? A genuine
    66	   open question for Stage 1/2, not decided here.]
    67	4. **Granularity and blocking-vs-advisory are policy-driven, not structural.** [Resolved,
    68	   per AJ-003 and the discovery doc's "Policy centralization" finding: this feature consults
    69	   a not-yet-briefed Policy Registry for review strategy (per-item, per-bundle, sampled,
    70	   blocking, advisory, risk-based skipping) rather than hardcoding one strategy for every
    71	   artifact type.]
    72	
    73	## Suspected Dependencies
    74	
    75	Upstream (hard): EA-0004 (Candidate Evidence), EA-0005 (constructed Ambiguities), and
    76	EA-0006 (Candidate Claims) — all three consumed directly. Also a not-yet-briefed Policy
    77	Registry feature, consulted for review strategy — recorded as a belief, not yet verified.
    78	
    79	Note on relationship shape: this is not a simple one-directional consumption. This
    80	feature's Accepted Evidence output feeds EA-0006 (Claim Construction), which produces
    81	Candidate Claims that come back to this same feature for review — a recurring, staged
    82	back-and-forth across the pipeline, not a cycle within a single pass.
    83	
    84	Downstream (hard): EA-0006 depends on this feature's Accepted Evidence output (per the
    85	correction already made to EA-0004's brief).
    86	
    87	Downstream (soft): eventual Publishing views and EA-0009 (Publication Review, once briefed)
    88	will likely consume this feature's accepted knowledge base (Accepted Evidence, Accepted
    89	Claims, resolved Ambiguities) as their source of truth.
    90	
    91	## Rough Scope Notes
    92	
    93	In scope (rough): evaluating Candidate Evidence, Candidate Claims, and Ambiguities for
    94	trustworthiness, using the distinct question appropriate to each; owning accept/reject/
    95	return-for-revision outcomes for each; routing human-initiated disagreement referrals to
    96	Ambiguity Construction; consulting the Policy Registry for review strategy.
    97	
    98	Out of scope (rough): producing any of the underlying candidates itself (each transformation
    99	feature's own job); investigation-level approval (EA-0007's job); publication-level approval
   100	(EA-0009's job, once briefed); defining the Policy Registry itself.
   101	
   102	## Readiness Check
   103	
   104	- [x] The problem statement explains WHY, not HOW
   105	- [x] The primary actor is a human role, not "the system"
   106	- [x] The core outcome is stated from the actor's perspective
   107	- [x] At least one open question is listed (four listed)
   108	- [x] Suspected dependencies are named (even if marked uncertain)
   109	- [x] No actor+outcome DBA form appears anywhere in this brief
   110	- [x] No stable guarantees or DBA scope boundaries appear in this brief (scope notes are
   111	      informal guardrails, not formal DBA contract language)
   112	- [x] The feature can be described without mentioning implementation technology
   113	- [x] (R-type only) — n/a, this is F-type
   114	
   115	**Brief status**: READY FOR STAGE 1
   116	
   117	---
   118	
   119	<!-- METADATA -->
   120	brief_created: 2026-07-17
   121	brief_last_updated: 2026-07-18
   122	stage1_started:

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
The artifact satisfies the brief-stage acceptance criteria.

Problem is clearly stated at `backlog/EA-0011-review_registry.md:17`: governance decisions exist across EA-0007/0008/0009 but require manual merging without a registry. The actor and outcome are human-centered at `EA-0011:26` and `EA-0011:33`. Scope is bounded at `EA-0011:75` and `EA-0011:79`, with unresolved boundaries left for Stage 1/2 at `EA-0011:48` and `EA-0011:55`. The proposed artifact is an append-only, queryable review ledger at `EA-0011:75`. Value/risk/guardrail are present through the audit-history value at `EA-0011:33`, open questions at `EA-0011:48-59`, and the no-authoring guardrail at `EA-0011:41` and `EA-0011:79`. No implementation technology is introduced, and the checklist explicitly says this remains a Stage 1/2 design principle rather than an approved DBA guarantee at `EA-0011:93`.

**Claim Support**
Strong claims are supported within the packet. EA-0011 claims the three source features produce canonical records at `EA-0011:17` and `EA-0011:63`; that is supported by EA-0007’s Investigation Approval record at `backlog/EA-0007-investigation_review.md:34`, EA-0008’s Knowledge Review record at `backlog/EA-0008-knowledge_review.md:43`, and EA-0009’s Publication Review record at `backlog/EA-0009-publication_review.md:37`. The “never edited”/append-only language at `EA-0011:44` is framed as a proposed design principle for Stage 1/2, not an implemented or approved guarantee, at `EA-0011:93`.

**Scope Drift**
No scope drift found. The additional EA-0008 and EA-0009 record-artifact statements directly support EA-0011’s source-record premise; no unrelated downstream doctrine modification is evident from the packet.

**In-Scope Blockers**
No IN-SCOPE BLOCKER findings.

PR decision: ADVANCE  
Scope drift warning: no — nothing in the packet pulls the PR beyond the review-registry brief’s stated scope.

LOG SUMMARY: NO OBJECTION — EA-0011 satisfies the brief-stage criteria with supported canonical source records
EVIDENCE: A
HIGHEST-IMPACT UNCERTAINTY: The packet notes uncommitted workspace changes, so the main uncertainty is whether these full-file contents exactly represent the intended review state.
tokens used
47,905
