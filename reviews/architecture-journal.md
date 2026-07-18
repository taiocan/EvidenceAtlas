# Architecture Journal

Cross-cutting institutional knowledge that outlives any single feature. Per-feature
review files (`reviews/[feature_id].md`) are traceability artifacts; this file is for
findings a future reader — who has forgotten the specific feature entirely — would still
benefit from. Entries are append-only; superseded entries are addressed by a new entry
referencing the old one, never by editing it.

---

## AJ-001 — Editorial Review Consolidation

Date: 2026-07-17
Status: Active

Context: Surfaced while feature-briefing EA-0001 (Research Brief), EA-0002 (Research
Planning), and EA-0003 (Corpus Construction) in sequence. Each proposes its own editor
checkpoint, and `backlog/initiate.md`'s three-tier Editorial Review Gate (Gate 1 evidence
acceptance / Gate 2 claim approval / Gate 3 publication judgement) hasn't even been briefed
yet — that's already up to six human decision points implied across a single investigation.

Finding: The cost of human judgment is becoming fragmented across many small,
independently-briefed checkpoints, each locally justified in its own brief but never
evaluated as a whole. This sharpens the discovery doc's own "editorial review is a design
space, not a fixed cost" finding
(`docs/solution-discovery-evidenceatlas.md`, Architectural Risks §8 P1) — the total review
burden, and whether checkpoints should be merged, made advisory, or eliminated, is
invisible if each feature brief only reasons about its own gate in isolation.

Decision: Deferred. Do not consolidate or resolve now, and do not force premature
consolidation into any single feature brief — features should still divide along their
natural boundaries (e.g. planning vs. execution). This is a system-level optimization to
make once the full pipeline is in view, not a per-feature decision.

Action: Track every proposed human decision point as each new feature brief is written.
Running tally so far:
  - EA-0001: Research Brief approval
  - EA-0002: Research Plan approval
  - EA-0003: corpus-gap/coverage decision (if escalated)
  - Not yet briefed: Gate 1 (evidence acceptance), Gate 2 (claim approval), Gate 3
    (publication judgement)
Before designing the Editorial Review Gate feature itself, evaluate whether some of these
should be merged, made advisory-only, or eliminated — minimizing total editorial cost
without weakening governance.

Supersedes: none
Related: none yet — will likely connect to whatever finding emerges when the Editorial
Review Gate candidate is briefed.

---

## AJ-002 — Actor-Role Fragmentation

Date: 2026-07-17
Status: Active

Context: Surfaced while feature-briefing EA-0004 (Evidence Extraction). Its primary actor
was named "Evidence Reviewer," distinct from the "Editor / Research Lead" used by
EA-0001 through EA-0003, on the grounds that the actor for each feature is whoever directly
engages with that feature's own output next. Gate 1/2/3 (not yet briefed) will likely
introduce further distinct role names (e.g. a Claim Reviewer, a Publication Reviewer).

Finding: The same underlying risk AJ-001 tracks for review-*checkpoint* count also applies
one level down, to actor-*role* count. Naming a distinct role per feature is architecturally
consistent — each named role really does reflect a different kind of judgment — but in a
real lean V1 team these roles are very likely the same one or two people wearing several
hats, not distinct staff. Fragmenting role names across briefs risks implying an
organizational structure that doesn't exist, the same way fragmenting checkpoints risks
implying more review cost than actually necessary.

Decision: Deferred, same posture as AJ-001 — keep naming roles precisely per feature during
briefing (don't force premature merging of roles just because one person may fill them),
but don't assume distinct role names imply distinct people.

Action: When the Editorial Review Gate feature is eventually briefed, and whenever a
role/actor inventory is assembled alongside AJ-001's checkpoint tally, note explicitly which
named roles are believed to collapse onto the same real person(s) in a lean V1, rather than
leaving that mapping implicit.

Supersedes: none
Related: AJ-001

---

## AJ-003 — Editorial Review Consolidation Resolved: Three Governance Classes, Decoupled from Transformation Features

Date: 2026-07-17
Status: Active

Context: AJ-001 tracked seven emerging human-decision points across EA-0001 through
EA-0006 without resolving how many should exist, explicitly deferring that decision until
the Editorial Review Gate feature itself was ready to be briefed. This entry records that
resolution.

Finding: The seven previously-tracked checkpoints (Brief approval, Plan approval,
corpus-gap escalation, Gate 1 evidence acceptance, Ambiguity approval, Gate 2 claim
approval, Gate 3 publication judgement) conflate two axes that don't need to mirror each
other: AI transformation features (one feature per epistemic operation — Research
Planning, Corpus Construction, Evidence Extraction, Claim Construction, Ambiguity
Construction) and human governance questions (a much smaller number of genuinely distinct
judgment types). Collapsing checkpoints by counting transformation features was the wrong
axis; the right axis is by governance question asked.

Decision: Reduce human governance to three classes, each its own feature, decoupled from
the transformation features that feed them:
  - **Investigation Review** — "is this the right investigation to perform?" Covers
    Research Brief and Research Plan approval as one governance phase (not necessarily one
    atomic decision — partial outcomes like "brief approved, plan sent back for revision"
    must remain possible within it).
  - **Knowledge Review** — "can I trust this knowledge representation?" Covers accepted
    Evidence, Candidate Claims, and Ambiguities as one class of judgment, even though it
    recurs at multiple points in time across the pipeline rather than firing once.
  - **Publication Review** — "should this leave the system?" Kept fully separate, no
    overlap with the other two.
  The corpus-gap escalation from EA-0003 is deliberately excluded from this checkpoint
  count — it's operational exception-handling (what to do when execution can't satisfy the
  plan), not a trust/governance judgment, even though it may occasionally surface a
  decision to a human. (Noted alternative view, not adopted: this could instead be modeled
  as a rare re-entry into Investigation Review, since "proceed despite gaps" does bear on
  trust in the resulting knowledge base — flagged for awareness, not acted on.)
  Review granularity (per-item, per-bundle, sampled, blocking, advisory) is a Policy
  Registry concern applied within each governance class, not a structural property that
  distinguishes separate gates.

Action: Brief Investigation Review, Knowledge Review, and Publication Review as three
separate F-type features. Investigation Review's brief must allow partial-approval
outcomes (not one atomic pass/fail across both artifacts). Knowledge Review's brief must be
explicit that it's a recurring governance activity applied at multiple pipeline points, not
a single point-in-time gate.

Supersedes: none
Related: AJ-001 (resolves the consolidation question that entry deferred), AJ-002 (actor
naming for these three features should reconcile against the already-tracked Evidence
Reviewer / Ambiguity Reviewer / Claim Reviewer roles, not add three more unrelated names)

---

## AJ-004 — Authority Layer: A Third Feature Class

Date: 2026-07-18
Status: Active

Context: Surfaced while resolving the Round 0 boundary question for Policy Registry, the
first of four not-yet-briefed governance-registry candidates (Policy, Dependency, Review,
Change Event) named in `initiate.md` §2 and carried through the discovery doc. Attempting to
brief Policy Registry using the same actor/outcome pattern as the prior nine features
produced an awkward, unmotivated actor ("a Policy Administrator maintains policies") that
didn't capture why the feature exists.

Finding: The architecture has organically produced a third feature class, not just two:
  - **Knowledge features** — transform material into new epistemic artifacts (EA-0002
    through EA-0006).
  - **Governance features** — human decisions about whether an artifact is fit to proceed
    (EA-0007 through EA-0009).
  - **Authority services** — declarative rules that modulate how other features behave,
    without transforming knowledge or making a review decision themselves (Policy
    Registry, and likely Dependency Registry, Review Registry, and Change Event Registry
    once each is briefed).
  Authority services differ from both other classes in scope and lifecycle: they're
  authored rarely, apply across many investigations rather than being scoped to one, and
  their "actor" question is best answered as "who authors/adjusts the rule," not "who
  benefits from a transformation or approves an artifact."

Decision: Continue briefing Authority-Layer candidates using the existing Feature Brief
template (it still captures Problem/Actor/Outcome/Scope adequately), explicitly labeled as
members of this third class rather than forced to read as transformation or governance
features. Do not invent a dedicated "Policy Administrator" (or similar) role for v1 — keep
Editor/Research Lead as the actor, since these are editorial-policy decisions, not
infrastructure administration; inventing a new role now would be premature specialization
(same reasoning as AJ-002). Policy changes themselves do not get a governance/review
checkpoint of their own (versioned and auditable, yes; a fourth review class, no) — but see
Policy Registry's own brief for an open question this raises: policy must be able to
configure *how* a governance checkpoint behaves without being able to configure it out of
existence entirely for content that would otherwise require it.

Action: When briefing Dependency Registry, Review Registry, and Change Event Registry,
check whether each is genuinely an Authority-Layer member, or actually belongs to one of
the first two classes — don't assume the label transfers automatically just because
`initiate.md` originally grouped them together.

Supersedes: none
Related: AJ-002 (role-fragmentation reasoning extended to Authority-Layer actors), AJ-003
(this is the layer beneath the pipeline that AJ-003's three governance classes consult for
policy-driven behavior)

---

## AJ-005 — Derived Index: A Fourth Feature Class, and Dependency Registry Deferred Until After Publishing

Date: 2026-07-18
Status: Active

Context: Applying AJ-004's own directive ("don't assume the Authority-Layer label
transfers automatically") to Dependency Registry, the second of `initiate.md`'s four
originally-grouped governance registries.

Finding: Dependency Registry does not fit the Authority Service class established in
AJ-004. Policy Registry is authoritative because a human authors normative rules other
features must obey; Dependency Registry is the opposite — it contains no human-authored
truth, should never be independently edited, and is correct only insofar as it faithfully
mirrors relationships that already exist elsewhere. This calls for a fourth structural
class: **Derived Index** — a feature that mechanically projects canonical relationships
already owned by other artifacts into a queryable reverse view, performing no epistemic
transformation, interpretation, or synthesis of its own. (The defining test is the absence
of epistemic transformation, not literal determinism — a Knowledge feature's output could
in principle be deterministic under the right constraints without stopping being an
epistemic transformation.)

Scoping this also surfaced that most "dependency" relationships already live on their
owning artifact (Candidate Evidence already stores its Research Question links; Claims
already store their Claim-Evidence relationships; Ambiguities already store their
competing Claims/Evidence) — the only relationship that cannot live on its source artifact
is the reverse one: a Claim/Ambiguity cannot know in advance which future Publishing
artifacts will reference it. Dependency Registry's real scope is this reverse lookup only,
not a general-purpose relationship graph, and it must not infer semantic dependence from
unstructured prose — only from explicit, structured references the not-yet-briefed
Publishing feature owns.

Decision: Defer Dependency Registry's full brief until after Publishing Engine/Publishing
Views is briefed, since Publishing owns the very relationships this index derives from
(what exactly is the referencing artifact, whether references are structured or inferred,
whether draft/withdrawn/superseded views are indexed, etc.) — briefing Dependency Registry
first would force it to invent assumptions that belong to Publishing. This reverses the
original "registries before Publishing" sequencing specifically for Dependency Registry,
since — unlike Policy Registry — its dependency direction runs the opposite way:
Publishing → Dependency Registry, not Dependency Registry → Publishing.

Action: Revised sequence: Policy Registry (done) → Review Registry / Change Event Registry
(still need their own classification checks per AJ-004's Action item) → Publishing
Engine/Publishing Views → Dependency Registry. When Review Registry and Change Event
Registry are checked, watch for the same Derived-Index possibility — Change Event Registry
in particular may turn out to be closer to a Derived Index, or even redundant with this
project's own DBA event log, per the discovery doc's existing note on that topic
(`docs/solution-discovery-evidenceatlas.md`, Architectural Risks §8 P1).

Supersedes: none
Related: AJ-004 (extends its "check, don't assume" directive; this entry is the first
application of it), AJ-003 (Publication Review, one of AJ-003's three governance classes,
will need to consult this index once both exist)

---

## AJ-006 — Derived Ledger: A Third Registry Sub-Class, Distinct from Both Authority and Index

Date: 2026-07-18
Status: Active

Context: Applying AJ-004/AJ-005's "check, don't assume" directive to Review Registry, the
third of `initiate.md`'s four originally-grouped governance registries.

Finding: Review Registry is neither an Authority Service (AJ-004) nor quite the same as the
Derived Index established for Dependency Registry (AJ-005). EA-0007, EA-0008, and EA-0009
each already own authoring their own canonical decision record (an Investigation Approval
record, a Knowledge Review record, a Publication Review record) — nothing else should
author these. Review Registry's role is to aggregate those three canonical records into one
queryable, append-only audit ledger, introducing no new authoring workflow and no business
logic of its own. The distinction from Dependency Registry: an Index answers "what
currently references this" (effectively a recomputable current-state view), while a Ledger
answers "what happened, in order, and it never changes" (an immutable historical record
where corrections happen only by appending a new entry, never editing an old one) — mirroring
the append-only Decision Log rule already established in `dba-system.md` and proven in
practice all session via `reviews/review-log.md` (decisions) and
`reviews/architecture-journal.md` (cross-cutting learning), which is itself the concrete
precedent for this split.

This produces a fuller taxonomy: the pipeline has two classes (**Knowledge** transformation
features, **Governance** review features, per AJ-004), and the shared infrastructure layer
beneath it has (at least) three: **Authority** (human-authored rules — Policy Registry),
**Ledger** (immutable historical decision records — Review Registry), and **Index**
(mechanically-derived current-state lookups — Dependency Registry).

Decision: Brief Review Registry as a derived governance ledger that aggregates the
canonical review records emitted by EA-0007/EA-0008/EA-0009, not as a feature that performs
independent review work. Immutability is explicit: entries are never edited, only appended
to (a correction is a new entry, not a rewrite). Two scope boundaries are left genuinely
open in the brief rather than decided here: whether Policy Registry's own change history
should live in this same ledger or stay separate, and whether EA-0003's corpus-gap
escalation (excluded from the governance checkpoint count by AJ-003) should still be logged
here when a human does make that call.

Action: When Change Event Registry is checked (per AJ-005's Action item), explicitly
compare it against this Ledger definition — `initiate.md` describes it as logging *any*
significant state change (not just human decisions), which may make it a broader event log
that Review Registry's ledger is a subset of, rather than a fourth distinct class. Resolve
that relationship explicitly rather than assuming they're unrelated or redundant.

Supersedes: none
Related: AJ-004 (extends its taxonomy), AJ-005 (Index vs. Ledger distinction), AJ-001/AJ-003
(this ledger is where the governance classes' decisions actually get recorded)

---

## AJ-007 — Change Event Registry Is the Second Ledger; Event Inventory Deferred to Stage 1, Not Assumed

Date: 2026-07-18
Status: Active

Context: Applying AJ-004/005/006's "check, don't assume" directive to Change Event
Registry, the last of `initiate.md`'s four originally-grouped governance registries. A
prior line of reasoning proposed retroactively adding "this feature emits event X"
statements to EA-0002 through EA-0010 before briefing this feature, so its "aggregates
events other features already emit" premise would be supported the way EA-0011's premise
needed EA-0008/EA-0009's small retroactive fix. That proposal was rejected.

Finding: Retroactively naming specific events across six-plus briefs would have been
premature for two reasons. First, it conflates two different-altitude decisions — whether
the architecture has canonical domain events at all (an architectural principle) versus
exactly which events each feature emits (a feature-specific contract) — and would have
resolved both by assumption in one editing pass, rather than deciding the principle once
and letting each feature's own later work derive its specific events. Second, and more
fundamentally, naming specific event identifiers is explicitly Stage 3 (Event Schema)
territory per `dba-system.md` ("the most constraining artifact — implementation is locked
to it," and "You NEVER emit events not listed in the approved event schema") — a Feature
Brief inserting event names would itself violate the doctrine this whole exercise operates
under, not merely be inelegant sequencing.

Decision: Brief Change Event Registry (EA-0012) with its dependency on upstream
event-emission left completely explicit and unresolved, not assumed. Formalize a
cross-ledger invariant, confirmed by this and the Review Registry precedent: **no ledger
may invent its own canonical records** — Review Registry aggregates review records
authored exclusively by the governance features (EA-0007/0008/0009); Change Event Registry
aggregates domain events that must be authored exclusively by the features whose state
actually transitions. Neither ledger is the canonical source of what it stores.

Action: EA-0012's own later work (or an explicit cross-cutting exercise, since an event
spine naturally spans multiple features rather than living inside any one) should produce
an inventory of required canonical domain events and identify which upstream feature owns
each one. Only after that inventory exists should EA-0002 through EA-0010 be amended
(through their own Stage 2/3 Contract and Event Schema work, not as retroactive brief
edits) to declare the specific events they emit.

Supersedes: none
Related: AJ-006 (extends the Ledger sub-class to a second member), AJ-004/AJ-005 (continues
the "check, don't assume" directive)

---

## AJ-008 — Post-Acceptance Lifecycle Ownership Unassigned for Evidence, Claims, and Ambiguities

Date: 2026-07-18
Status: Active

Context: Surfaced while briefing EA-0013 (Publishing). The original discovery-doc
vocabulary includes lifecycle states like "challenged," "superseded," and "retired" for
Evidence, Claims, and Ambiguities — but no briefed feature (EA-0004, EA-0005, EA-0006, or
EA-0008) currently owns transitioning an artifact into those states after initial
acceptance. Each feature's brief stops at "accepted"; nothing describes what happens when
new evidence later contradicts something already accepted.

Finding: This is the same shape of gap as AJ-007 (a lifecycle was assumed to exist without
an owning feature) — assumed here, not yet made explicit as an unresolved dependency in any
brief.

Decision: Not resolved now — flagged for awareness. Likely candidates when it is addressed:
this could be additional scope for EA-0008 (Knowledge Review, since it already owns
accept/reject for these artifact types) or a new feature, but that should be decided
deliberately rather than assumed when it comes up.

Action: Before treating any feature's knowledge-acceptance lifecycle as complete, check
whether post-acceptance transitions (challenged, superseded, retired) have an owner.

Supersedes: none
Related: AJ-007 (same gap shape — assumed lifecycle, no owner)
