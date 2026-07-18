---
review_id: REV__publishing__brief__R1
findings: []
unparsed_findings_count: 0
reviewed:
  feature: publishing
  stage: brief
  branch: main
  base_commit: (no base pin)
  review_commit: aa5be800de44b6dd7ac02a88eddb163baf5d85ff
  artifacts:
    - path: backlog/EA-0013-publishing.md
      sha256: 1922bdba998aa9c893194ca14cc06af936574449b58bcde8e118cd5f5b3a9569
      visibility: shown
    - path: backlog/EA-0008-knowledge_review.md
      sha256: fdd794cfb039152c5db156acddd38cf03a5f0d6e2dccbff1b5e0e5b5b76bb790
      visibility: shown
    - path: backlog/EA-0009-publication_review.md
      sha256: 303634b939ee5cf46155d9f87f8bd091a6342db22ce01913d18722b0d7eae81d
      visibility: shown
  diff_hash: e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
  coverage_state: FULL_COVERAGE
  workspace_dirty: true
  redaction_count: 0
  secret_redaction: false
  excluded_paths: []
  reviewed_packet: packets/20260718T082556Z-publishing-stage-brief-aa5be80.packet.txt
  reviewed_packet_sha256: 4750ddd6d88f74bab4c21d7bcd645ec98f0c13f29dc6222f3c57a9718559039c
  reviewer: "codex (session 019f7454-58ce-7483-a234-469c5c6c2fe4)"
  codex_concern: NO OBJECTION
  effective_concern: NO OBJECTION
  evidence: A
  reasoning_effort: high
  reconnect_count: 0
  elapsed_ms: 44576
---

**Acceptance Criteria**

EA-0013 satisfies the brief-stage criteria.

- Problem clearly stated: yes, [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:13) explains why accepted knowledge needs purpose-specific publication views.
- Scope bounded: yes, in-scope and out-of-scope notes are explicit at [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:122).
- No implementation detail: mostly yes. Rendering tech is named only to exclude it from scope, not to prescribe implementation, at [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:44) and [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:129).
- Ready to become Stage 1 Intent: yes, it declares `READY FOR STAGE 1` at [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:150), with readiness checks at lines 135-148.
- Value/risk/guardrail present: yes. Value is reuse and consistent framing at lines 15-22 and 36-40. Risk is misrepresentation/lost provenance at lines 66-69 and 70-73. Guardrails include no self-approval at lines 112-114 and rendering/dependency indexing out of scope at lines 129-133.

**Claim Support**

No acceptance-blocking unsupported strong claim found. Strong claims such as “never inferred” and “must never self-approve” are supported as explicit scope/guardrail statements within the brief itself: [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:66), [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:112). The claim that this resolves AJ-005 is not independently verifiable from the packet because AJ-005 is not included, but it does not affect brief-stage acceptance on the supplied criteria.

**Scope Drift**

No scope drift found in the packet. EA-0013 stays at brief level and explicitly leaves exact state model, content-unit typology, rendering, dependency indexing, and formal approval enforcement to later work: [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:74), [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:88), [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:129).

**In-Scope Blockers**

None found.

**Findings**

No IN-SCOPE BLOCKER findings.

PR decision: ADVANCE  
Scope drift warning: no — nothing in the packet pulls the brief beyond its stated Stage Brief scope.

LOG SUMMARY: NO OBJECTION — EA-0013 satisfies the stated brief-stage criteria with no in-scope blockers.
EVIDENCE: A
HIGHEST-IMPACT UNCERTAINTY: The packet does not include AJ-005, so the “resolves AJ-005” claim is not independently verifiable here.
OpenAI Codex v0.142.5
--------
workdir: /home/rimo/projects/EvidenceAtlas
model: gpt-5.5
provider: openai
approval: never
sandbox: read-only
reasoning effort: high
reasoning summaries: none
session id: 019f7454-58ce-7483-a234-469c5c6c2fe4
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
  generated: 2026-07-18T08:25:11Z
  task_prompt: /home/rimo/projects/Codeos/prompts/codeos-reviewer-task.md (4959 bytes)
  review_content_bytes: 21988
  estimated_review_tokens: ~5497
  budget_status: OK
  packet_mode: full
  delta_base: none
  items:
    - path: backlog/EA-0013-publishing.md
      mode: full_file
      bytes: 9643
      sha256: 1922bdba998aa9c893194ca14cc06af936574449b58bcde8e118cd5f5b3a9569
    - path: backlog/EA-0008-knowledge_review.md
      mode: full_file
      bytes: 6641
      sha256: fdd794cfb039152c5db156acddd38cf03a5f0d6e2dccbff1b5e0e5b5b76bb790
    - path: backlog/EA-0009-publication_review.md
      mode: full_file
      bytes: 5704
      sha256: 303634b939ee5cf46155d9f87f8bd091a6342db22ce01913d18722b0d7eae81d
    - path: (diff)
      mode: full_file
      bytes: 0

REVIEW CONTEXT
  Feature:                publishing
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
  --- backlog/EA-0013-publishing.md (sha256: 1922bdba998aa9c893194ca14cc06af936574449b58bcde8e118cd5f5b3a9569, visibility: shown) ---
    # Feature Brief: EA-0013 — Publishing
    
    **Slug**: publishing
    **Type**: F-type
    **Refines**: n/a
    **Tier**: 0 — Foundational, last pipeline (Knowledge-transformation) feature. Resolves
    Architecture Journal AJ-005's deferred questions about the referencing artifact Dependency
    Registry will eventually index.
    **Status**: BRIEF-DRAFT
    
    ---
    
    ## Problem / Need
    
    Accepted Claims and Ambiguities exist, but nothing yet turns them into a purpose-specific
    representation for a reader — an Article, a Reality Check, a Decision Brief, or a future
    Topic Page all need to select a subset of accepted knowledge, arrange and frame it for a
    specific audience and purpose, and preserve exactly which Claim or Ambiguity backs each
    part of what's said. Without this, either every view has to be assembled ad hoc with no
    consistent framing discipline, or the same reviewed knowledge can't be reused across
    multiple views the way `initiate.md` identifies as the project's main source of
    scalability.
    
    ## Primary Actor
    
    A **Publishing Editor** role, distinct from the Knowledge Reviewer (EA-0008) and Editor/
    Research Lead (EA-0001/EA-0002/EA-0007) — the person deciding which accepted Claims and
    Ambiguities belong in a given view and how they should be framed for its audience. The
    review question differs from every prior role: not "is this fit for acceptance" or "is this
    the right investigation," but "does this representation serve its intended purpose and
    audience." The same person may fill this role too in v1; noted for Architecture Journal
    AJ-002's tally regardless.
    
    ## Core Outcome (informal)
    
    The Publishing Editor can produce a structured, reviewable composition — a **Publishing
    View Revision** — that selects specific accepted Claims and Ambiguities, frames each one
    (fact, interpretation, recommendation, or caveat), and arranges them for a specific view
    type, without needing to invent framing conventions from scratch each time or losing track
    of which underlying knowledge backs each part of the result.
    
    ## Design Tensions and Open Questions
    
    1. **Publishing vs. Presentation.** [Resolved: this feature owns content selection,
       framing, and composition — deciding which Claims/Ambiguities are included and how
       they're framed. Markdown/MDX serialization, HTML/Astro generation, JSON-LD, typography,
       and other rendering concerns are a separate, downstream concern (Presentation), out of
       scope here. Publication Review (EA-0009) reviews the structured composition this feature
       produces, not the rendered output — keeping content correctness from getting entangled
       with rendering.]
    2. **One feature for all view types, not one per type.** [Resolved: Article, Reality Check,
       Decision Brief, and future Topic Page share substantial behavior — consuming accepted
       knowledge, selecting a subset, framing and arranging it, preserving provenance,
       supporting revision and lifecycle. What differs is composition policy per view type
       (e.g. an Article emphasizes narrative, a Decision Brief separates evidence/assumptions/
       options/recommendations), not the underlying transformation. Splitting into four
       features would duplicate the lifecycle, reference model, and review relationship for no
       real gain.]
    3. **What is the canonical referencing artifact, resolving AJ-005?** [Resolved: the
       **Publishing View Revision** — not the abstract Publication, and not the rendered
       output. A Publication is a stable identity across its lifetime (e.g. "EU Battery
       Regulation: Strategic Implications"); each Publishing View Revision is an immutable
       content composition at a point in time, and is the artifact that actually carries
       Claim/Ambiguity references. Rendered output is a separate, mechanical projection of one
       approved revision — not itself a source of dependency truth.]
    4. **Explicit references, never inferred.** [Resolved: every use of a Claim or Ambiguity
       must be represented explicitly and structurally within the revision itself — never
       inferred later by scanning rendered prose. This is what makes reliable impact analysis,
       correction, and withdrawal possible.]
    5. **Can one revision reference both Claims and Ambiguities?** [Resolved: yes, and often
       must — publishing a contested Claim without its accompanying Ambiguity would risk
       exactly the misrepresentation EA-0009 exists to prevent. Claims and Ambiguities stay
       distinguishable roles within a revision, not flattened into one undifferentiated list.]
    6. **What granularity do references attach at?** [Resolved in principle, not in exact
       vocabulary: references attach to structured **content units** within a revision (e.g.
       something like a section, an evidence block, a recommendation, a caveat — illustrative,
       not a locked taxonomy), with revision-level and publication-level dependency views
       derived from those. A flat whole-view reference list is too coarse — if a Claim changes,
       the editor needs to know where and for what purpose it was used, not just that some
       article somewhere cites it. The specific content-unit typology is left to Stage 1/2, to
       avoid the same premature-ontology problem already avoided twice for "Evidence
       Category."]
    7. **Do revisions replace or coexist?** [Resolved: coexist. A revision is immutable once
       created; a newer revision can supersede an older one, but never erases or rewrites it.
       Each revision retains its own references, so both "what does the current revision depend
       on" and "what did an earlier revision depend on" stay answerable — this is what keeps
       the eventual Dependency Registry's history honest rather than lossy.]
    8. **Lifecycle ownership.** [Resolved in principle: this feature owns the Publication's and
       its revisions' lifecycle (creating drafts, producing revisions after requested changes,
       marking a reviewed revision published, superseding, withdrawing) — but never the
       approval decision itself, which stays exclusively EA-0009's. **The exact state model is
       tentative, not settled** — something like Draft → Under Review → Approved → Published →
       Superseded, with Withdrawn reachable from Approved or Published, is a reasonable
       candidate, and keeping Approved and Published as distinct states (approval means the
       content is acceptable; published means it's actually externally active) is worth
       preserving since it supports scheduled/embargoed release without making EA-0009
       responsible for the operational act of publishing. Needs Stage 1/2 to confirm the actual
       states and transitions, consistent with how every other lifecycle in this project has
       been treated.]
    9. **How much history does this feature retain?** [Resolved: all of it. Draft, superseded,
       and withdrawn revisions are never discarded — only a full revision history lets the
       eventual Dependency Registry answer both "what do currently published revisions depend
       on" and "has this Claim ever appeared in any public output." What query views Dependency
       Registry exposes over that history is that feature's own scope to define, not this one's.]
    
    ## Suspected Dependencies
    
    Upstream (hard): EA-0008's accepted knowledge base (Accepted Evidence indirectly, Accepted
    Claims and Ambiguities directly) — this feature composes from what Knowledge Review has
    already accepted, never from Candidate-stage material.
    
    Downstream (hard): EA-0009 (Publication Review) consumes Publishing View Revisions
    directly and owns the approve/reject/request-revision decision on them — this feature must
    never self-approve.
    
    Downstream (soft, forward): the not-yet-briefed Dependency Registry will index this
    feature's structured Claim/Ambiguity references across all revisions; a separate,
    not-yet-briefed Presentation capability will render an approved revision into Markdown/MDX/
    HTML/Astro output — not yet confirmed as a domain feature versus a purely technical
    capability.
    
    ## Rough Scope Notes
    
    In scope (rough): selecting accepted Claims and Ambiguities for a given view type;
    composing and framing them into structured content units; producing an immutable Publishing
    View Revision with explicit references; owning Publication/revision identity and lifecycle
    (draft, revision, published, superseded, withdrawn) short of the approval decision itself.
    
    Out of scope (rough): accepting or rejecting knowledge (EA-0008's job); approving
    publication correctness (EA-0009's job); rendering technology, layout, or typography
    (Presentation's job, once/if briefed); inferring dependencies from rendered prose;
    dependency reverse-indexing itself (the not-yet-briefed Dependency Registry's job); a fixed
    content-unit taxonomy (left to Stage 1/2).
    
    ## Readiness Check
    
    - [x] The problem statement explains WHY, not HOW
    - [x] The primary actor is a human role, not "the system"
    - [x] The core outcome is stated from the actor's perspective
    - [x] At least one open question is listed (nine listed; most resolved as principles, #6 and
          #8 explicitly flagged as needing Stage 1/2 confirmation rather than settled)
    - [x] Suspected dependencies are named (even if marked uncertain)
    - [x] No actor+outcome DBA form appears anywhere in this brief
    - [x] No stable guarantees or DBA scope boundaries appear in this brief (the lifecycle and
          content-unit descriptions are proposed design candidates for Stage 1/2, not approved
          DBA contracts)
    - [x] The feature can be described without mentioning implementation technology
    - [x] (R-type only) — n/a, this is F-type
    
    **Brief status**: READY FOR STAGE 1
    
    ---
    
    <!-- METADATA -->
    brief_created: 2026-07-18
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

  --- backlog/EA-0009-publication_review.md (sha256: 303634b939ee5cf46155d9f87f8bd091a6342db22ce01913d18722b0d7eae81d, visibility: shown) ---
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
    
    Downstream, publication flow: none — this is the last internal checkpoint before external
    visibility; what comes after is publication itself, not another pipeline feature.
    
    Downstream, registry consumer: EA-0011 (Review Registry) aggregates this feature's
    Publication Review records (added 2026-07-18) — this is a registry relationship, not
    another stage in the publication flow itself.
    
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

DIFF TO REVIEW (base->review, secret/size filtered)

codex
I’ll cite the packeted artifact files directly and keep this to the stated brief-stage scope. I’m only checking the claims and acceptance criteria the packet actually shows.
exec
/bin/bash -lc "nl -ba backlog/EA-0013-publishing.md | sed -n '1,220p'" in /home/rimo/projects/EvidenceAtlas
 succeeded in 0ms:
     1	# Feature Brief: EA-0013 — Publishing
     2	
     3	**Slug**: publishing
     4	**Type**: F-type
     5	**Refines**: n/a
     6	**Tier**: 0 — Foundational, last pipeline (Knowledge-transformation) feature. Resolves
     7	Architecture Journal AJ-005's deferred questions about the referencing artifact Dependency
     8	Registry will eventually index.
     9	**Status**: BRIEF-DRAFT
    10	
    11	---
    12	
    13	## Problem / Need
    14	
    15	Accepted Claims and Ambiguities exist, but nothing yet turns them into a purpose-specific
    16	representation for a reader — an Article, a Reality Check, a Decision Brief, or a future
    17	Topic Page all need to select a subset of accepted knowledge, arrange and frame it for a
    18	specific audience and purpose, and preserve exactly which Claim or Ambiguity backs each
    19	part of what's said. Without this, either every view has to be assembled ad hoc with no
    20	consistent framing discipline, or the same reviewed knowledge can't be reused across
    21	multiple views the way `initiate.md` identifies as the project's main source of
    22	scalability.
    23	
    24	## Primary Actor
    25	
    26	A **Publishing Editor** role, distinct from the Knowledge Reviewer (EA-0008) and Editor/
    27	Research Lead (EA-0001/EA-0002/EA-0007) — the person deciding which accepted Claims and
    28	Ambiguities belong in a given view and how they should be framed for its audience. The
    29	review question differs from every prior role: not "is this fit for acceptance" or "is this
    30	the right investigation," but "does this representation serve its intended purpose and
    31	audience." The same person may fill this role too in v1; noted for Architecture Journal
    32	AJ-002's tally regardless.
    33	
    34	## Core Outcome (informal)
    35	
    36	The Publishing Editor can produce a structured, reviewable composition — a **Publishing
    37	View Revision** — that selects specific accepted Claims and Ambiguities, frames each one
    38	(fact, interpretation, recommendation, or caveat), and arranges them for a specific view
    39	type, without needing to invent framing conventions from scratch each time or losing track
    40	of which underlying knowledge backs each part of the result.
    41	
    42	## Design Tensions and Open Questions
    43	
    44	1. **Publishing vs. Presentation.** [Resolved: this feature owns content selection,
    45	   framing, and composition — deciding which Claims/Ambiguities are included and how
    46	   they're framed. Markdown/MDX serialization, HTML/Astro generation, JSON-LD, typography,
    47	   and other rendering concerns are a separate, downstream concern (Presentation), out of
    48	   scope here. Publication Review (EA-0009) reviews the structured composition this feature
    49	   produces, not the rendered output — keeping content correctness from getting entangled
    50	   with rendering.]
    51	2. **One feature for all view types, not one per type.** [Resolved: Article, Reality Check,
    52	   Decision Brief, and future Topic Page share substantial behavior — consuming accepted
    53	   knowledge, selecting a subset, framing and arranging it, preserving provenance,
    54	   supporting revision and lifecycle. What differs is composition policy per view type
    55	   (e.g. an Article emphasizes narrative, a Decision Brief separates evidence/assumptions/
    56	   options/recommendations), not the underlying transformation. Splitting into four
    57	   features would duplicate the lifecycle, reference model, and review relationship for no
    58	   real gain.]
    59	3. **What is the canonical referencing artifact, resolving AJ-005?** [Resolved: the
    60	   **Publishing View Revision** — not the abstract Publication, and not the rendered
    61	   output. A Publication is a stable identity across its lifetime (e.g. "EU Battery
    62	   Regulation: Strategic Implications"); each Publishing View Revision is an immutable
    63	   content composition at a point in time, and is the artifact that actually carries
    64	   Claim/Ambiguity references. Rendered output is a separate, mechanical projection of one
    65	   approved revision — not itself a source of dependency truth.]
    66	4. **Explicit references, never inferred.** [Resolved: every use of a Claim or Ambiguity
    67	   must be represented explicitly and structurally within the revision itself — never
    68	   inferred later by scanning rendered prose. This is what makes reliable impact analysis,
    69	   correction, and withdrawal possible.]
    70	5. **Can one revision reference both Claims and Ambiguities?** [Resolved: yes, and often
    71	   must — publishing a contested Claim without its accompanying Ambiguity would risk
    72	   exactly the misrepresentation EA-0009 exists to prevent. Claims and Ambiguities stay
    73	   distinguishable roles within a revision, not flattened into one undifferentiated list.]
    74	6. **What granularity do references attach at?** [Resolved in principle, not in exact
    75	   vocabulary: references attach to structured **content units** within a revision (e.g.
    76	   something like a section, an evidence block, a recommendation, a caveat — illustrative,
    77	   not a locked taxonomy), with revision-level and publication-level dependency views
    78	   derived from those. A flat whole-view reference list is too coarse — if a Claim changes,
    79	   the editor needs to know where and for what purpose it was used, not just that some
    80	   article somewhere cites it. The specific content-unit typology is left to Stage 1/2, to
    81	   avoid the same premature-ontology problem already avoided twice for "Evidence
    82	   Category."]
    83	7. **Do revisions replace or coexist?** [Resolved: coexist. A revision is immutable once
    84	   created; a newer revision can supersede an older one, but never erases or rewrites it.
    85	   Each revision retains its own references, so both "what does the current revision depend
    86	   on" and "what did an earlier revision depend on" stay answerable — this is what keeps
    87	   the eventual Dependency Registry's history honest rather than lossy.]
    88	8. **Lifecycle ownership.** [Resolved in principle: this feature owns the Publication's and
    89	   its revisions' lifecycle (creating drafts, producing revisions after requested changes,
    90	   marking a reviewed revision published, superseding, withdrawing) — but never the
    91	   approval decision itself, which stays exclusively EA-0009's. **The exact state model is
    92	   tentative, not settled** — something like Draft → Under Review → Approved → Published →
    93	   Superseded, with Withdrawn reachable from Approved or Published, is a reasonable
    94	   candidate, and keeping Approved and Published as distinct states (approval means the
    95	   content is acceptable; published means it's actually externally active) is worth
    96	   preserving since it supports scheduled/embargoed release without making EA-0009
    97	   responsible for the operational act of publishing. Needs Stage 1/2 to confirm the actual
    98	   states and transitions, consistent with how every other lifecycle in this project has
    99	   been treated.]
   100	9. **How much history does this feature retain?** [Resolved: all of it. Draft, superseded,
   101	   and withdrawn revisions are never discarded — only a full revision history lets the
   102	   eventual Dependency Registry answer both "what do currently published revisions depend
   103	   on" and "has this Claim ever appeared in any public output." What query views Dependency
   104	   Registry exposes over that history is that feature's own scope to define, not this one's.]
   105	
   106	## Suspected Dependencies
   107	
   108	Upstream (hard): EA-0008's accepted knowledge base (Accepted Evidence indirectly, Accepted
   109	Claims and Ambiguities directly) — this feature composes from what Knowledge Review has
   110	already accepted, never from Candidate-stage material.
   111	
   112	Downstream (hard): EA-0009 (Publication Review) consumes Publishing View Revisions
   113	directly and owns the approve/reject/request-revision decision on them — this feature must
   114	never self-approve.
   115	
   116	Downstream (soft, forward): the not-yet-briefed Dependency Registry will index this
   117	feature's structured Claim/Ambiguity references across all revisions; a separate,
   118	not-yet-briefed Presentation capability will render an approved revision into Markdown/MDX/
   119	HTML/Astro output — not yet confirmed as a domain feature versus a purely technical
   120	capability.
   121	
   122	## Rough Scope Notes
   123	
   124	In scope (rough): selecting accepted Claims and Ambiguities for a given view type;
   125	composing and framing them into structured content units; producing an immutable Publishing
   126	View Revision with explicit references; owning Publication/revision identity and lifecycle
   127	(draft, revision, published, superseded, withdrawn) short of the approval decision itself.
   128	
   129	Out of scope (rough): accepting or rejecting knowledge (EA-0008's job); approving
   130	publication correctness (EA-0009's job); rendering technology, layout, or typography
   131	(Presentation's job, once/if briefed); inferring dependencies from rendered prose;
   132	dependency reverse-indexing itself (the not-yet-briefed Dependency Registry's job); a fixed
   133	content-unit taxonomy (left to Stage 1/2).
   134	
   135	## Readiness Check
   136	
   137	- [x] The problem statement explains WHY, not HOW
   138	- [x] The primary actor is a human role, not "the system"
   139	- [x] The core outcome is stated from the actor's perspective
   140	- [x] At least one open question is listed (nine listed; most resolved as principles, #6 and
   141	      #8 explicitly flagged as needing Stage 1/2 confirmation rather than settled)
   142	- [x] Suspected dependencies are named (even if marked uncertain)
   143	- [x] No actor+outcome DBA form appears anywhere in this brief
   144	- [x] No stable guarantees or DBA scope boundaries appear in this brief (the lifecycle and
   145	      content-unit descriptions are proposed design candidates for Stage 1/2, not approved
   146	      DBA contracts)
   147	- [x] The feature can be described without mentioning implementation technology
   148	- [x] (R-type only) — n/a, this is F-type
   149	
   150	**Brief status**: READY FOR STAGE 1
   151	
   152	---
   153	
   154	<!-- METADATA -->
   155	brief_created: 2026-07-18
   156	brief_last_updated: 2026-07-18
   157	stage1_started:

exec
/bin/bash -lc "nl -ba backlog/EA-0008-knowledge_review.md | sed -n '1,180p'" in /home/rimo/projects/EvidenceAtlas
exec
/bin/bash -lc "nl -ba backlog/EA-0009-publication_review.md | sed -n '1,180p'" in /home/rimo/projects/EvidenceAtlas
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
    72	Downstream, publication flow: none — this is the last internal checkpoint before external
    73	visibility; what comes after is publication itself, not another pipeline feature.
    74	
    75	Downstream, registry consumer: EA-0011 (Review Registry) aggregates this feature's
    76	Publication Review records (added 2026-07-18) — this is a registry relationship, not
    77	another stage in the publication flow itself.
    78	
    79	## Rough Scope Notes
    80	
    81	In scope (rough): confirming a published view's content and framing accurately reflect the
    82	accepted knowledge base, including required framing for contested or ambiguous points;
    83	consulting the Policy Registry for applicable publication-time policies.
    84	
    85	Out of scope (rough): generating the published view itself (the not-yet-briefed Publishing
    86	feature's job); proofreading, formatting, or rendering (Presentation Layer's job);
    87	re-litigating Knowledge Review's own accept/reject decisions, which are already settled by
    88	the time a view reaches this feature.
    89	
    90	## Readiness Check
    91	
    92	- [x] The problem statement explains WHY, not HOW
    93	- [x] The primary actor is a human role, not "the system"
    94	- [x] The core outcome is stated from the actor's perspective
    95	- [x] At least one open question is listed (four listed)
    96	- [x] Suspected dependencies are named (even if marked uncertain)
    97	- [x] No actor+outcome DBA form appears anywhere in this brief
    98	- [x] No stable guarantees or DBA scope boundaries appear in this brief (scope notes are
    99	      informal guardrails, not formal DBA contract language)
   100	- [x] The feature can be described without mentioning implementation technology
   101	- [x] (R-type only) — n/a, this is F-type
   102	
   103	**Brief status**: READY FOR STAGE 1
   104	
   105	---
   106	
   107	<!-- METADATA -->
   108	brief_created: 2026-07-17
   109	brief_last_updated: 2026-07-18
   110	stage1_started:

codex
**Acceptance Criteria**

EA-0013 satisfies the brief-stage criteria.

- Problem clearly stated: yes, [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:13) explains why accepted knowledge needs purpose-specific publication views.
- Scope bounded: yes, in-scope and out-of-scope notes are explicit at [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:122).
- No implementation detail: mostly yes. Rendering tech is named only to exclude it from scope, not to prescribe implementation, at [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:44) and [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:129).
- Ready to become Stage 1 Intent: yes, it declares `READY FOR STAGE 1` at [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:150), with readiness checks at lines 135-148.
- Value/risk/guardrail present: yes. Value is reuse and consistent framing at lines 15-22 and 36-40. Risk is misrepresentation/lost provenance at lines 66-69 and 70-73. Guardrails include no self-approval at lines 112-114 and rendering/dependency indexing out of scope at lines 129-133.

**Claim Support**

No acceptance-blocking unsupported strong claim found. Strong claims such as “never inferred” and “must never self-approve” are supported as explicit scope/guardrail statements within the brief itself: [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:66), [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:112). The claim that this resolves AJ-005 is not independently verifiable from the packet because AJ-005 is not included, but it does not affect brief-stage acceptance on the supplied criteria.

**Scope Drift**

No scope drift found in the packet. EA-0013 stays at brief level and explicitly leaves exact state model, content-unit typology, rendering, dependency indexing, and formal approval enforcement to later work: [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:74), [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:88), [backlog/EA-0013-publishing.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0013-publishing.md:129).

**In-Scope Blockers**

None found.

**Findings**

No IN-SCOPE BLOCKER findings.

PR decision: ADVANCE  
Scope drift warning: no — nothing in the packet pulls the brief beyond its stated Stage Brief scope.

LOG SUMMARY: NO OBJECTION — EA-0013 satisfies the stated brief-stage criteria with no in-scope blockers.
EVIDENCE: A
HIGHEST-IMPACT UNCERTAINTY: The packet does not include AJ-005, so the “resolves AJ-005” claim is not independently verifiable here.
tokens used
18,214
