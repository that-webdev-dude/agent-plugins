# Project state

The lead keeps `gamedevs-state.json` in the game project, using [this template](../assets/project-state.json) only for a new run. Reuse existing state and planning artifacts. Only the lead writes it. This file is a checkpoint, not proof that work happened or executable gate enforcement.

Fill the brief from user input and approved decisions; it is an orientation summary, not a competing contract. Keep only active tasks, essential evidence and useful artifact references. Use project-relative paths where possible; never store credentials. Record interview checkpoints, phase changes, approvals, blockers and handoff, rather than every tool call.

Schema version 2 phases: `PLANNING`, `ART`, `SLICE`, `PRODUCTION`, `DELIVERY`.

Status: `ACTIVE`, `AWAITING_INTERVIEW_ANSWERS`, `AWAITING_CONTRACT_APPROVAL`, `AWAITING_ART_APPROVAL`, `AWAITING_SLICE_APPROVAL`, `BLOCKED_ENGINE`, `BLOCKED_EXTERNAL`, `COMPLETE`.

## Planning checkpoint

`planning` stores a small index, not a second design document:

- `round`: current issued interview round number, incremented when a new round is presented.
- `pendingQuestions`: exact issued questions, their numbers/IDs and recommendations, retained until answered or explicitly withdrawn. Preserve partial answers in the contract decision history and retain the unanswered questions.
- `unresolvedDecisions` and `provisionalDecisions`: IDs/links to the contract entries, with no duplicated normative text.
- `contractRevision`: current draft or approved contract revision; `approvedContractRevision`: last explicitly approved revision, null until approval. They can differ while an amendment is pending.
- `resume`: previous phase/status when planning interrupts an existing run, otherwise null. Save enough context to resume the affected work without resetting valid gates.
- `nextTicket`: project-relative reference to the next useful ticket, even if it is waiting on a gate. A pointer is not permission to execute it.

Record contract, roadmap and ticket locations under `artifacts`, reusing existing document paths. `remainingWork` indexes active ticket paths, rather than maintaining a duplicate backlog. The contract owns requirements and decisions; each ticket owns its execution status/result. State records the current gate and pointers. A READY ticket still cannot bypass a newer blocker, owner message or stale approval.

When asking a round, set `phase: PLANNING` and `status: AWAITING_INTERVIEW_ANSWERS`; save all pending questions, then wait. Record settled decisions as answers arrive. When the package is reviewable, set `AWAITING_CONTRACT_APPROVAL` and identify its exact artifacts. Neither status permits game implementation, asset production or a specialist substituting its answers for the owner's. Authorized draft documentation, read-only feasibility work and responses to the pending planning work are allowed.

## Approvals and dispatch

Each approval records the actual human message or a concise attributable quotation, date, and the exact artifact/build revision approved. `approvals.contract` also identifies the reviewed roadmap and ticket baseline. Use a stable revision/hash with retained content or an equivalent snapshot; a mutable file path alone cannot identify what was approved. Preserve superseded/stale approvals under `approvalHistory` before replacing a current entry. Never invent approval or convert a pending status to approved because a timestamp passed. If the owner changes an approved decision, mark only affected approvals stale and retain why and what they approved.

Art/slice approvals also identify any within-bounds provisional-choice resolution presented with that artifact. These versioned contract addenda supplement the approved revision without overwriting its snapshot; store their references with the relevant gate and artifacts. A changed requirement outside the approved bounds follows amendment approval instead.

On contract approval, set `approvedContractRevision` to the approved revision and update `approvals.contract`. Enter `ART / ACTIVE` for a new game, or resume the saved phase/status only if its prerequisites and existing approvals remain valid. A focused change may reuse unaffected art/slice approvals; do not reset them automatically. If planning-only, retain `PLANNING` with the next action stating that the package was handed off and execution awaits an owner request; do not mark the game COMPLETE. Approval of the package does not itself broaden authorized work.

When the owner later requests implementation of an approved planning-only package, revalidate its artifacts, approval and current project baseline. If still valid, enter `ART / ACTIVE` or the saved applicable phase and dispatch the first ready ticket; do not repeat the interview or contract approval. Changed requirements or a materially changed baseline need the focused amendment/reconciliation described below.

For an amendment, retain the last approved snapshot and revision, set the draft `contractRevision`, record the affected tickets/approvals and block affected dispatch. Independent, already-authorized work may continue only if the lead explicitly records that it remains valid against the approved contract. An owner-approved amendment updates only affected gates and requirements; a routine fix within the agreement does not need a new approval.

Before dispatch, check the current status, contract revision, ticket readiness/dependencies, permissions, prerequisites and latest owner messages. An awaiting art/slice status permits only requested revisions and their focused checks, not downstream work. A blocked status permits diagnosis, requested remediation or already-bounded independent work, not dependent production. On a fresh session, verify artifact existence, contract/ticket revisions and current engine/build identity; do not rerun all accepted checks unless relevant files changed. If required approval evidence or its artifact is missing, recover it from trusted chat history or present the affected artifact for approval again. Never infer approval from the recorded phase, ticket completion or a revision field alone.

## Migrate older runs

Read and preserve the actual version-1 state; never overwrite it with a fresh template. Add version-2 fields and set `schemaVersion: 2`, retaining existing brief, artifacts, evidence, blockers, work and approval records. Keep `approvals.concept` as historical evidence when present; it does not become a contract approval. Add `approvals.contract: null` and planning defaults only where missing. Do not turn previous concept, art or slice approval into a new approval or discard its evidence.

For new implementation in a legacy run without a contract, save the previous phase/status in `planning.resume` and enter `PLANNING`. `CONCEPT / AWAITING_CONCEPT_APPROVAL` becomes planning for the contract, reusing the existing concept as input. For a later phase, confirm the relevant baseline or requested change with the owner and recover valid existing art/slice gate evidence; resume that phase after contract approval when its prerequisites are satisfied. Preserve an engine/external blocker and its resume condition during planning; contract approval alone never clears it.

Do not restart a completed run or require a new contract for a report-only request, final-report completion or read-only review. For a small requested implementation change, the contract may be a focused agreement covering that change and affected baseline. Only questions needed for that scope belong in its rounds.

## Handoff and completion

For interruptions or context loss, leave the pending round, next useful action and unresolved blocker explicit. On completion record the approved contract revision, delivered artifact, launch instructions and actual requirement evidence. Required provisional choices and acceptance criteria must be resolved; closed tickets alone do not establish completion. Once written, record `GAMEDEV-REPORT.md` under `artifacts.finalReport`; writing the report does not reopen a completed game. A state file cannot keep a process running after Codex stops or restart it on its own.
