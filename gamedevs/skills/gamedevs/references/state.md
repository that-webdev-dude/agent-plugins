# Project state

The lead keeps `gamedevs-state.json` in the game project, using [this template](../assets/project-state.json) only for a new run. Reuse existing state and planning artifacts. Only the lead writes it. This file is a checkpoint, not proof that work happened or executable gate enforcement.

Fill the brief from user input and approved decisions. Keep only active tasks, essential evidence and useful artifact references. Use project-relative paths where possible; never store credentials. Record phase changes, approvals, blockers and handoff, rather than every tool call.

Phases: `CONCEPT`, `ART`, `SLICE`, `PRODUCTION`, `DELIVERY`.

Status: `ACTIVE`, `AWAITING_CONCEPT_APPROVAL`, `AWAITING_ART_APPROVAL`, `AWAITING_SLICE_APPROVAL`, `BLOCKED_ENGINE`, `BLOCKED_EXTERNAL`, `COMPLETE`.

Each approval records the actual human message or a concise attributable quotation, date, and the exact artifact/build revision approved. Use a stable revision/hash or retained snapshot; a mutable file path alone cannot identify what was approved. Never invent approval or convert a pending status to approved because a timestamp passed. If the user changes an approved decision, mark only the affected approval stale and retain the history needed to understand the current state.

Before dispatch, check the current status, prerequisites and latest user messages. An awaiting status permits only requested revisions and their focused checks, not downstream work. A blocked status permits diagnosis, requested remediation or already-bounded independent work, not dependent production. On a fresh session, verify artifact existence and current engine/build identity; do not rerun all accepted checks unless relevant files changed. If required approval evidence or its artifact is missing, recover it from trusted chat history or present the affected artifact for approval again. Never infer approval from the recorded phase alone.

For interruptions or context loss, leave the next useful action and unresolved blocker explicit. On completion record the delivered artifact, launch instructions and actual evidence. Once written, record `GAMEDEV-REPORT.md` under `artifacts.finalReport`; writing the report does not reopen a completed game. A state file cannot keep a process running after Codex stops or restart it on its own.
