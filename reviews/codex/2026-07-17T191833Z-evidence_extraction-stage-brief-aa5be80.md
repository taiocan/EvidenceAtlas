---
review_id: REV__evidence_extraction__brief__R2
findings: []
unparsed_findings_count: 0
reviewed:
  feature: evidence_extraction
  stage: brief
  branch: main
  base_commit: (no base pin)
  review_commit: aa5be800de44b6dd7ac02a88eddb163baf5d85ff
  artifacts:
    - path: backlog/EA-0004-evidence_extraction.md
      sha256: 6575810777a2b288d81092cdb207a52c7541e6fca7508bdf731bee5fae57a5e3
      visibility: shown
  diff_hash: e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
  coverage_state: FULL_COVERAGE
  workspace_dirty: true
  redaction_count: 0
  secret_redaction: false
  excluded_paths: []
  reviewed_packet: packets/20260717T191833Z-evidence_extraction-stage-brief-aa5be80.packet.txt
  reviewed_packet_sha256: aee2f31d33fc3a9f32705635d33f9ff7d2275f6d4a9e4b86f783f1a15f46df9b
  reviewer: "codex (session 019f7169-b419-7e60-86ff-48b32db3502d)"
  codex_concern: NO OBJECTION
  effective_concern: NO OBJECTION
  evidence: A
  reasoning_effort: high
  reconnect_count: 0
  elapsed_ms: 59204
---

**Acceptance Criteria**

- Problem clearly stated: satisfied. The brief explains the evidence gap and downstream traceability risk at [backlog/EA-0004-evidence_extraction.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:11).
- Scope explicitly bounded: satisfied. In-scope and out-of-scope boundaries are stated at [line 126](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:126), including approved-corpus-only extraction and no claim construction.
- No implementation detail: satisfied for brief stage. The artifact describes conceptual checks and outputs, not implementation technology or mechanics.
- Ready to become Stage 1 Intent: satisfied. Status is `BRIEF-DRAFT`, with `Brief status: READY FOR STAGE 1` at [line 158](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:158).
- Value/risk/guardrail present: satisfied. Value appears in the problem and outcome sections; guardrails include no acceptance assertion at [line 63](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:63) and no new source discovery at [line 91](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:91).
- Proposed artifact(s): satisfied. The output is provisional `Candidate Evidence`, named at [line 97](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:97) and scoped at [line 135](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:135).

**Claim Support**

Strong claims are supported enough for this stage. The “may never assert accepted” and “approved Research Corpus only” claims are framed as scope guardrails and are consistently repeated in the scope section. The downstream claims about Claim Construction and EA-0005 are not independently verifiable from this packet, but they are dependency-context notes, not acceptance claims for this brief.

**Scope Drift**

No scope drift found. The brief discusses downstream dependencies, but does not modify downstream artifacts in the packet and keeps EA-0004 itself bounded to Candidate Evidence production.

**In-Scope Blockers**

No IN-SCOPE BLOCKER findings.

PR decision: ADVANCE

Scope drift warning: no — dependency notes are within expected brief scope and do not expand EA-0004 behavior.

LOG SUMMARY: NO OBJECTION — The brief satisfies the Stage Brief criteria with no in-scope blockers.
EVIDENCE: A
HIGHEST-IMPACT UNCERTAINTY: The assessment most depends on treating the EA-0005 and Claim Construction references as contextual dependency notes rather than binding downstream doctrine.
OpenAI Codex v0.142.5
--------
workdir: /home/rimo/projects/EvidenceAtlas
model: gpt-5.5
provider: openai
approval: never
sandbox: read-only
reasoning effort: high
reasoning summaries: none
session id: 019f7169-b419-7e60-86ff-48b32db3502d
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
  generated: 2026-07-17T19:17:34Z
  task_prompt: /home/rimo/projects/Codeos/prompts/codeos-reviewer-task.md (4959 bytes)
  review_content_bytes: 10510
  estimated_review_tokens: ~2627
  budget_status: OK
  packet_mode: full
  delta_base: none
  items:
    - path: backlog/EA-0004-evidence_extraction.md
      mode: full_file
      bytes: 10510
      sha256: 6575810777a2b288d81092cdb207a52c7541e6fca7508bdf731bee5fae57a5e3
    - path: (diff)
      mode: full_file
      bytes: 0

REVIEW CONTEXT
  Feature:                evidence_extraction
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
  --- backlog/EA-0004-evidence_extraction.md (sha256: 6575810777a2b288d81092cdb207a52c7541e6fca7508bdf731bee5fae57a5e3, visibility: shown) ---
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
    
    The **Evidence Reviewer** — a distinct role from the Editor / Research Lead used by
    EA-0001–EA-0003 (the same person may fill both roles in v1, but the responsibility is
    different: this role evaluates whether a proposed candidate evidence item is suitable to
    enter the project's evidence base, not whether an investigation strategy is sound). Today,
    without this feature, that evaluation can't happen at all — the reviewer would have to
    search raw documents, choose passages, interpret them, and reconstruct relevance themselves,
    which is exactly the duplicated, inconsistent work this feature exists to remove.
    
    ## Core Outcome (informal)
    
    The Evidence Reviewer can efficiently determine whether a proposed candidate evidence item
    is suitable to become part of the project's evidence base — without having to reconstruct
    the research process or rediscover the supporting material themselves. The feature has
    already done the expensive preparation (locating the passage, capturing it faithfully,
    interpreting it, and explaining why it belongs to the investigation); the reviewer's job
    becomes evaluation, not investigation. Concretely, that single "fit for acceptance"
    decision rests on three distinguishable questions later Stage 1/2 work should keep
    separate: was the right passage *selected* for this Research Question, does the
    *interpretation* stay grounded in what the passage actually says, and does that
    interpretation actually *advance* the Research Question it's linked to. This feature
    doesn't decide any of the three — it produces evidence structured so a reviewer (or a
    later, not-yet-briefed Gate 1 feature) can decide efficiently.
    
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
    2. **Where's the line between this feature's self-verification and Gate 1's acceptance
       decision?** [Resolved as a principle: this feature may only verify narrow, structural/
       grounding properties — the source belongs to the approved corpus, the locator resolves
       to the cited passage, the excerpt is faithful and unaltered (truncation disclosed),
       sufficient context was captured, required fields are present, the interpretation doesn't
       visibly introduce facts absent from the source, and duplicate/overlapping records are
       flagged. It may never assert that a candidate is *accepted* — only that it's
       structurally complete and apparently grounded. The "visibly introduce unsupported
       facts" check sits closest to the line, since it requires some semantic comparison, not
       pure structure-checking — flagged for Stage 1/2 to tighten if needed. Everything about
       substantive acceptance (does the interpretation actually hold up, is it too broad, are
       qualifications missing, accept/reject/return-for-revision) belongs to a separate,
       not-yet-briefed Editorial Review Gate feature. These are recorded here as **assumptions
       requiring validation by that future brief**, not decisions this feature owns.]
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
    
    Downstream (hard): a not-yet-briefed Editorial Review Gate feature (Gate 1 — evidence
    acceptance) consumes Candidate Evidence directly. The accept/reject/return-for-revision
    behavior implied by Gate 1, and the expectation that any revised interpretation produces a
    traceable new version rather than a silent rewrite, are recorded here as assumptions for
    that future brief to validate, not decisions this feature makes.
    
    **Correction (2026-07-17, during EA-0006 Round 0):** Claim Construction does **not**
    consume Candidate Evidence directly, despite what an earlier version of this section said.
    It consumes Gate-1-*accepted* Evidence — otherwise unreviewed, possibly-hallucinated
    candidates could influence claim synthesis before the human acceptance step meant to catch
    that. The chain is Candidate Evidence → Gate 1 → Accepted Evidence → Claim Construction;
    Claim Construction's dependency on Candidate Evidence is indirect, mediated through Gate 1.
    
    Downstream (soft): EA-0005 (Ambiguity Construction) is the deliberate exception to the
    correction above — its pre-claim path explicitly accepts manually-referred Candidate
    Evidence pairs directly, without requiring Gate 1 acceptance first, since that path is
    explicitly analytical/provisional (it can conclude "no real conflict" or "insufficient
    context") and doesn't promote those candidates into the accepted evidence base. Not a hard
    dependency in the sense of being required for this feature to run, but worth keeping in
    mind when that feature is eventually briefed, since `initiate.md`'s original
    contradiction-handling flow only considered ambiguity emerging at the claim level.
    
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
    the future Editorial Review Gate feature); contradiction or ambiguity reasoning; claim
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
    brief_last_updated: 2026-07-17
    stage1_started:

DIFF TO REVIEW (base->review, secret/size filtered)

codex
I’ll pin the review to the shown artifact and use the local file only to recover line numbers for citations; I won’t treat anything outside the packet as evidence.
exec
/bin/bash -lc 'sha256sum backlog/EA-0004-evidence_extraction.md' in /home/rimo/projects/EvidenceAtlas
 succeeded in 0ms:
6575810777a2b288d81092cdb207a52c7541e6fca7508bdf731bee5fae57a5e3  backlog/EA-0004-evidence_extraction.md

exec
/bin/bash -lc "nl -ba backlog/EA-0004-evidence_extraction.md | sed -n '1,180p'" in /home/rimo/projects/EvidenceAtlas
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
    23	The **Evidence Reviewer** — a distinct role from the Editor / Research Lead used by
    24	EA-0001–EA-0003 (the same person may fill both roles in v1, but the responsibility is
    25	different: this role evaluates whether a proposed candidate evidence item is suitable to
    26	enter the project's evidence base, not whether an investigation strategy is sound). Today,
    27	without this feature, that evaluation can't happen at all — the reviewer would have to
    28	search raw documents, choose passages, interpret them, and reconstruct relevance themselves,
    29	which is exactly the duplicated, inconsistent work this feature exists to remove.
    30	
    31	## Core Outcome (informal)
    32	
    33	The Evidence Reviewer can efficiently determine whether a proposed candidate evidence item
    34	is suitable to become part of the project's evidence base — without having to reconstruct
    35	the research process or rediscover the supporting material themselves. The feature has
    36	already done the expensive preparation (locating the passage, capturing it faithfully,
    37	interpreting it, and explaining why it belongs to the investigation); the reviewer's job
    38	becomes evaluation, not investigation. Concretely, that single "fit for acceptance"
    39	decision rests on three distinguishable questions later Stage 1/2 work should keep
    40	separate: was the right passage *selected* for this Research Question, does the
    41	*interpretation* stay grounded in what the passage actually says, and does that
    42	interpretation actually *advance* the Research Question it's linked to. This feature
    43	doesn't decide any of the three — it produces evidence structured so a reviewer (or a
    44	later, not-yet-briefed Gate 1 feature) can decide efficiently.
    45	
    46	## Design Tensions and Open Questions
    47	
    48	1. **Should this be one feature, or split into passage-selection and interpretation?**
    49	   [Resolved: one feature. The deciding test is the same one that justified splitting
    50	   EA-0002 from EA-0003: does the earlier stopping point have independent actor value? A
    51	   Research Plan does — an editor can review a strategy before spending resources. A pile
    52	   of highlighted-but-uninterpreted passages doesn't — no reviewer benefits from evaluating
    53	   spans of text with no sense of what they're claimed to support. A future split would be
    54	   scalability-driven (very large corpora, separate retrieval models, passage reuse across
    55	   many interpretations at scale), not a mechanical-vs-interpretive one — not applicable for
    56	   v1.]
    57	2. **Where's the line between this feature's self-verification and Gate 1's acceptance
    58	   decision?** [Resolved as a principle: this feature may only verify narrow, structural/
    59	   grounding properties — the source belongs to the approved corpus, the locator resolves
    60	   to the cited passage, the excerpt is faithful and unaltered (truncation disclosed),
    61	   sufficient context was captured, required fields are present, the interpretation doesn't
    62	   visibly introduce facts absent from the source, and duplicate/overlapping records are
    63	   flagged. It may never assert that a candidate is *accepted* — only that it's
    64	   structurally complete and apparently grounded. The "visibly introduce unsupported
    65	   facts" check sits closest to the line, since it requires some semantic comparison, not
    66	   pure structure-checking — flagged for Stage 1/2 to tighten if needed. Everything about
    67	   substantive acceptance (does the interpretation actually hold up, is it too broad, are
    68	   qualifications missing, accept/reject/return-for-revision) belongs to a separate,
    69	   not-yet-briefed Editorial Review Gate feature. These are recorded here as **assumptions
    70	   requiring validation by that future brief**, not decisions this feature owns.]
    71	3. **What happens when no passage can be found for a Research Question?** [Resolved:
    72	   report it explicitly as an investigation finding, not a retrieval failure — e.g. "no
    73	   candidate evidence identified in the approved corpus for RQ-3." This says nothing about
    74	   reality, only about what this corpus contains, and is itself valuable information rather
    75	   than an error to hide.]
    76	4. **What happens when one passage is relevant to multiple Research Questions?**
    77	   [Resolved: extract once, link to many — a single candidate evidence item can reference
    78	   several Research Questions rather than being duplicated per question. Duplicating it
    79	   would create multiple copies of the same evidence that could drift independently, the
    80	   same "multiple mutable sources of truth" risk already flagged architecturally in
    81	   `docs/solution-discovery-evidenceatlas.md`.]
    82	5. **How should corroboration between independent sources be distinguished from mechanical
    83	   duplication?** [Resolved as a principle: this feature may recognize mechanical
    84	   duplication (e.g. a wire-service article republished verbatim) but must not collapse
    85	   independent agreement between genuinely distinct sources into "duplicate" — that
    86	   agreement is valuable signal for later stages, not redundancy. This feature doesn't
    87	   reason about *what* corroboration means or aggregate it; it only avoids destroying the
    88	   distinction. **Open nuance:** telling "mechanically identical/republished" apart from
    89	   "independently produced but agreeing" is itself a judgment call that isn't fully
    90	   specified here — left for Stage 2 to define concretely.]
    91	6. **Does this feature do any new source discovery?** [Resolved: no, hard boundary. It
    92	   operates only over the already-approved Research Corpus from EA-0003 — no web search,
    93	   no new crawling, no "just one more source." Crossing this boundary would make the
    94	   provenance chain impossible to reconstruct.]
    95	7. **Naming:** the feature name "Evidence Extraction" stays workable (it matches the
    96	   discovery doc's existing vocabulary — Evidence is already defined as excerpt +
    97	   interpretation), but its *output* should use provisional language (e.g. "Candidate
    98	   Evidence") rather than implying accepted evidence emerges automatically.
    99	
   100	## Suspected Dependencies
   101	
   102	Upstream: EA-0003 (Research Corpus + Research Execution Report) only.
   103	
   104	Downstream (hard): a not-yet-briefed Editorial Review Gate feature (Gate 1 — evidence
   105	acceptance) consumes Candidate Evidence directly. The accept/reject/return-for-revision
   106	behavior implied by Gate 1, and the expectation that any revised interpretation produces a
   107	traceable new version rather than a silent rewrite, are recorded here as assumptions for
   108	that future brief to validate, not decisions this feature makes.
   109	
   110	**Correction (2026-07-17, during EA-0006 Round 0):** Claim Construction does **not**
   111	consume Candidate Evidence directly, despite what an earlier version of this section said.
   112	It consumes Gate-1-*accepted* Evidence — otherwise unreviewed, possibly-hallucinated
   113	candidates could influence claim synthesis before the human acceptance step meant to catch
   114	that. The chain is Candidate Evidence → Gate 1 → Accepted Evidence → Claim Construction;
   115	Claim Construction's dependency on Candidate Evidence is indirect, mediated through Gate 1.
   116	
   117	Downstream (soft): EA-0005 (Ambiguity Construction) is the deliberate exception to the
   118	correction above — its pre-claim path explicitly accepts manually-referred Candidate
   119	Evidence pairs directly, without requiring Gate 1 acceptance first, since that path is
   120	explicitly analytical/provisional (it can conclude "no real conflict" or "insufficient
   121	context") and doesn't promote those candidates into the accepted evidence base. Not a hard
   122	dependency in the sense of being required for this feature to run, but worth keeping in
   123	mind when that feature is eventually briefed, since `initiate.md`'s original
   124	contradiction-handling flow only considered ambiguity emerging at the claim level.
   125	
   126	## Rough Scope Notes
   127	
   128	In scope (rough): locating candidate passages relevant to the approved Research Questions,
   129	within the approved Research Corpus only; capturing exact excerpts with resolvable
   130	provenance and sufficient context; producing a bounded interpretation per passage plus a
   131	short selection rationale explaining why it belongs to the investigation; linking each
   132	candidate evidence item to one or more Research Questions; running the narrow structural/
   133	grounding preflight checks listed above; explicitly reporting when no candidate evidence is
   134	found for a Research Question; recognizing mechanical duplication while preserving
   135	corroboration signal; emitting results as provisional Candidate Evidence pending
   136	acceptance.
   137	
   138	Out of scope (rough): any new source discovery, web search, or crawling (stays inside
   139	EA-0003's boundary); the substantive acceptance decision (accept/reject/revise — belongs to
   140	the future Editorial Review Gate feature); contradiction or ambiguity reasoning; claim
   141	construction; reasoning about what corroboration *means* or aggregating corroborating
   142	evidence (a later feature's job — this feature only preserves the distinction from
   143	duplication); canonical ownership of the "Evidence Category" vocabulary term (left
   144	intentionally open per EA-0002, for the same premature-ontology reason).
   145	
   146	## Readiness Check
   147	
   148	- [x] The problem statement explains WHY, not HOW
   149	- [x] The primary actor is a human role, not "the system"
   150	- [x] The core outcome is stated from the actor's perspective
   151	- [x] At least one open question is listed (seven listed)
   152	- [x] Suspected dependencies are named (even if marked uncertain)
   153	- [x] No actor+outcome DBA form appears anywhere in this brief
   154	- [x] No stable guarantees or DBA scope boundaries appear in this brief
   155	- [x] The feature can be described without mentioning implementation technology
   156	- [x] (R-type only) — n/a, this is F-type
   157	
   158	**Brief status**: READY FOR STAGE 1
   159	
   160	---
   161	
   162	<!-- METADATA -->
   163	brief_created: 2026-07-17
   164	brief_last_updated: 2026-07-17
   165	stage1_started:

codex
**Acceptance Criteria**

- Problem clearly stated: satisfied. The brief explains the evidence gap and downstream traceability risk at [backlog/EA-0004-evidence_extraction.md](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:11).
- Scope explicitly bounded: satisfied. In-scope and out-of-scope boundaries are stated at [line 126](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:126), including approved-corpus-only extraction and no claim construction.
- No implementation detail: satisfied for brief stage. The artifact describes conceptual checks and outputs, not implementation technology or mechanics.
- Ready to become Stage 1 Intent: satisfied. Status is `BRIEF-DRAFT`, with `Brief status: READY FOR STAGE 1` at [line 158](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:158).
- Value/risk/guardrail present: satisfied. Value appears in the problem and outcome sections; guardrails include no acceptance assertion at [line 63](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:63) and no new source discovery at [line 91](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:91).
- Proposed artifact(s): satisfied. The output is provisional `Candidate Evidence`, named at [line 97](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:97) and scoped at [line 135](/home/rimo/projects/EvidenceAtlas/backlog/EA-0004-evidence_extraction.md:135).

**Claim Support**

Strong claims are supported enough for this stage. The “may never assert accepted” and “approved Research Corpus only” claims are framed as scope guardrails and are consistently repeated in the scope section. The downstream claims about Claim Construction and EA-0005 are not independently verifiable from this packet, but they are dependency-context notes, not acceptance claims for this brief.

**Scope Drift**

No scope drift found. The brief discusses downstream dependencies, but does not modify downstream artifacts in the packet and keeps EA-0004 itself bounded to Candidate Evidence production.

**In-Scope Blockers**

No IN-SCOPE BLOCKER findings.

PR decision: ADVANCE

Scope drift warning: no — dependency notes are within expected brief scope and do not expand EA-0004 behavior.

LOG SUMMARY: NO OBJECTION — The brief satisfies the Stage Brief criteria with no in-scope blockers.
EVIDENCE: A
HIGHEST-IMPACT UNCERTAINTY: The assessment most depends on treating the EA-0005 and Claim Construction references as contextual dependency notes rather than binding downstream doctrine.
tokens used
19,398
