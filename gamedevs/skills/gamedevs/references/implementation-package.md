# Implementation package

Use this format during [game planning](game-planning.md). Adapt existing authoritative project documents instead of producing parallel specifications. Otherwise use `plans/game/CONTRACT.md`, `plans/game/ROADMAP.md` and `plans/game/tickets/T-001-descriptive-title.md`. Keep execution prompts inside their tickets and the planning handoff inside the roadmap. A small change can use equivalent sections in one existing plan. These are defaults, not mandatory filenames or a request to write into the plugin.

## Authority and identity

The owner-approved contract governs scope and acceptance. The roadmap sequences it; tickets organize execution; prompts load those artifacts; `gamedevs-state.json` tracks progress and pointers. A ticket cannot silently change a requirement. Keep rationale with its contract decision and reference it elsewhere instead of maintaining competing copies.

Give the contract an explicit revision. Retain the exact reviewed contract and package baseline through an existing/authorized commit, content hashes with retained snapshots, or equivalent stable artifact identities. Do not create a commit just to record approval without authorization. A draft revision and the last approved revision must be distinguishable. Record approval status in state without rewriting the reviewed snapshot. Package approval records the contract, roadmap and reviewed ticket identities; later elaboration inside that agreement can proceed without repeated approval. The state record identifies the current files and approval evidence; filenames alone are insufficient.

Record an experiment's findings in its ticket result. To settle a provisional contract choice within its approved bounds, present the exact resolution record alongside the art/slice artifact at the specified gate. Retain that record as a versioned contract addendum, with its identity in the gate approval; do not silently rewrite the original approved clauses. This uses the existing gate, not an extra approval ceremony. A change outside the agreed bounds needs the contract amendment process.

## Contract

Use concise sections covering:

1. **Identity and baseline:** project, revision, approval-record reference, owner, destination, current build/asset baseline and existing approvals to preserve. Do not invent an owner name or approval.
2. **Experience and rules:** player actions, core loop, goals/outcomes, controls, session structure, progression and content commitments.
3. **Presentation:** art/audio direction, camera, display/scale, readability, relevant animation/effects/UI/accessibility and approved references. Detailed art-production values may be provisional pending the sample.
4. **Technical and delivery constraints:** engine/version, target environments, performance/resource limits, pipeline, deliverable and exact definition of local completion. Explicitly include/exclude saves, networking and services when relevant.
5. **Scope and exclusions:** required outcomes and bounded optional choices. Excluded work cannot silently return as a future ticket.
6. **Requirements and acceptance:** stable IDs with observable criteria, verifier and expected evidence. Distinguish automated checks, observed target-runtime behavior and owner acceptance. Human fun is not a test assertion.
7. **Decisions and uncertainty:** approved decisions with rationale/evidence and provenance; unresolved decisions with dependencies; provisional decisions with experiments, bounds, resolver and blocked work. Use a brief glossary only where terms need definition.
8. **Responsibilities and authority:** owner inputs and approvals, agent responsibilities, permitted actions, resource limits and actions needing additional authorization. Contract approval does not imply permission to publish, post issues, change the engine or perform unrelated operations.
9. **Gates and amendments:** exact contract/art/slice approval conditions, what can proceed between them and how changes are approved. Retain superseded decisions and affected approval history without duplicating the active requirements.

Requirement format, expanded only as needed:

| ID and outcome | Acceptance criteria | Verification and responsibility | Dependencies / provisional status |
| --- | --- | --- | --- |
| R-001 — descriptive required behavior | Observable outcome under specified conditions | Focused check, runtime evidence or owner review; identify which | Decision/experiment IDs or none |

Avoid vague acceptance such as "polished" without concrete observable expectations and a named human review where subjective judgment remains.

## Roadmap

Describe all agreed scope at milestone level. Explain sequencing in terms of prerequisites and risks rather than an arbitrary calendar. Use actual dates/estimates only when supplied or explicitly agreed.

| Milestone and outcome | Why now / prerequisites | Related requirements and tickets | Entry gate | Exit evidence / owner approval |
| --- | --- | --- | --- | --- |
| M-01 — representative art / bounded feasibility evidence | Resolve the presentation or platform risk before expansion | Linked requirement and ticket titles | Approved contract and applicable prerequisites | Actual sample/evidence and art approval when applicable |
| M-02 — complete playable segment | Integrate approved assets and resolve gameplay uncertainty | Linked requirement and ticket titles | Art approval and ready dependencies | Tested controls, feedback, outcome and retry; owner play and slice approval |
| M-03 — agreed remaining content | Expand the proven loop and asset pipeline | Linked requirement and ticket titles | Slice approval | Contract criteria and focused ticket evidence |
| M-04 — local delivery | Verify the real delivery entry point | Linked requirement and ticket titles | Required content and decisions complete | Target artifact, launch evidence, credits and final coverage |

Adapt milestones to the actual game or change. In a focused existing-project fix, unaffected art/slice gates may already be satisfied. If an engine/platform risk requires a different initial experiment, put that bounded experiment first and block expansion on its result. Contract approval permits only the work allowed by its current gates; it never makes production tickets ready on its own.

Keep a small dependency graph or table identifying ticket prerequisites, decision/experiment dependencies and approval gates. Dependencies must be acyclic or explicitly identified as an unresolved planning blocker. Give every requirement a ticket/milestone link; every ticket needs an agreed outcome or approved experiment to justify its existence. Keep "Not yet specified" items attached to the milestone they block and elaborate them when evidence allows. Do not invent detailed implementation steps for unknown future decisions.

## Implementation tickets

Each ticket has one coherent, verifiable outcome. Split when parts have different prerequisites, owners or independently useful results. Do not size by arbitrary file count or pretend to know session duration.

```markdown
# T-001 — Descriptive outcome

Status: DRAFT | BLOCKED | READY | ACTIVE | DONE
Milestone: linked title and ID
Contract: project-relative path and approved revision
Requirements / decisions: linked IDs
Role: designer | artist | developer | tester (as appropriate)

## Outcome
Concrete result and why the agreement needs it.

## Scope and exclusions
Included work, affected behavior/assets and boundaries; preserve unrelated work.

## Prerequisites and gates
Required ticket results, settled decisions, artifacts and owner approvals.
For a blocked outline, state what is missing and what will make it executable.

## Implementation guidance
Verified project paths, relevant APIs/conventions and constraints.
Separate facts from proposed approaches; leave routine choices to the implementer.

## Acceptance criteria
Observable conditions linked to the contract requirements.

## Verification and evidence
Appropriate project checks, focused behavior checks, target-runtime observation
or owner review; identify the evidence to retain and what remains human judgment.

## Ownership and stop conditions
Assigned role, permitted writes, handoff, blockers and decisions to escalate.

## Execution prompt
Instantiated prompt using the format below, referencing this ticket and contract.

## Result
On execution: changed artifacts, check results, requirement evidence, limitations
and next dependency unlocked. DONE requires actual results, not a planned command.
```

Only set `READY` when prerequisites are satisfied, acceptance and verification are specific enough, permissions cover the work and current gates allow it. Distinguish a fully specified ticket waiting only on approval from an outline blocked on unknown design inputs. The former can include its copy-ready prompt now, explicitly conditional on the gate; the latter has an outcome, requirement links and named missing inputs, with its prompt section pending until it can be elaborated. Neither may execute while blocked. Active assignment is recorded by the lead before dispatch to avoid duplicate work. A single ticket file is authoritative for its result; state/roadmap link it rather than copying a backlog.

## Execution prompts

Put a copy-ready prompt in every executable ticket. Replace the explanatory fields below with actual project-relative paths, IDs, approved revision and permitted work; do not ship placeholder-only prompts as ready work. Prompts reference requirements instead of restating and potentially changing them. When revisions change, validate prompts before dispatch.

```text
Use $gamedevs in the intended game workspace to execute [ticket title and path].
Read the project's instructions, gamedevs-state.json, [contract path and approved
revision], the ticket's referenced requirements/decisions and [role reference].
Check current files against the approved baseline, latest owner instructions,
ticket dependencies, permissions and contract/art/slice approval gates.

Perform only this ticket's agreed outcome. Permitted writes: [actual ownership
scope]. Preserve unrelated work. Use the ticket's verified guidance and acceptance
criteria; propose amendments for changed requirements instead of implementing them.
Stop affected work for unmet prerequisites, stale approval, conflicting requirements
or the ticket's named blockers; report the evidence and next required decision.
The prompt grants no authority beyond the approved request and current gate.

Run the ticket's applicable checks and retain its requested evidence. Return changed
paths/artifacts, commands and observed results, requirement coverage, unverified
areas and blockers to the lead. The lead alone updates shared state and dispatches
downstream work. No specialist may approve its own gate. Human review remains human.
```

For a direct owner execution prompt, gamedevs acts as lead and dispatches the ticket to its assigned role. For a specialist task, the lead supplies the same context and constraints directly with the exact role-reference path; the specialist does not recursively invoke gamedevs or create a team. These prompts do not install dependencies, create external tracker issues, publish or authorize engine changes.

## Planning handoff

Include in the roadmap:

- contract/package revision and exact artifacts presented or approved;
- owner approval evidence, or an explicit statement that approval is pending;
- included milestones, exclusions and material provisional decisions;
- unresolved decisions and the work they block;
- first executable milestone and linked ticket prompts, conditional on approval where still pending;
- authorization to implement, or planning-only status;
- next useful action and required owner input.

Before presenting for approval, check requirement coverage, ticket dependencies/gates, prompt references and readiness. Do not label an unapproved package approved, or a currently gated ticket READY; identify the ticket that becomes executable when approval arrives. At final delivery, reuse these links to show each requirement's actual evidence and disclose gaps rather than treating closed tickets as proof.
