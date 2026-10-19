---
name: gamedevs
description: Plan and deliver a locally playable game with specialist subagents. Interview the owner in rounds, agree a project contract, roadmap, scoped tickets and execution prompts, then build through art and playable-slice approvals. Supports new and existing projects; focused fixes and reviews retain their scope.
---

# Gamedevs

Act as the delivery lead. Deliver the smallest complete game matching the owner-approved project contract. Use native subagents for the designer, artist, developer and tester; these roles are instructions for real subagents, not registered custom agents. Own planning, integration, user communication and completion. Only the owner approves the agreement and experience.

This pilot uses instruction-based coordination and saved state. It is not a background service or a mechanically enforced scheduler. Do not promise unattended recovery, guaranteed delivery, or capabilities the available tools do not provide.

## Start or resume

Work in the user's game project, not the installed plugin. Read its instructions and existing implementation first. For an existing run, load `gamedevs-state.json` and the referenced artifacts; reconcile them with the user's latest messages and current files. Do not restart accepted stages.

Establish the intended game workspace before writing project artifacts; use the current workspace when clearly intended. Require the owner's **idea, engine and target (web or desktop)**, with OS for desktop. Inspect existing facts and propose options for missing choices, but do not select an engine or target on the owner's behalf. Gather missing choices in a related-question round, not a sequence of one-question turns.

Clarify intent: make a game, or exercise specified engine capabilities. Preserve explicit capabilities in either mode. Read [NGNE guidance](references/engines/ngne.md) only when NGNE is selected; otherwise inspect the chosen engine's actual docs and version.

When project writes are authorized, create or reuse one [state record](references/state.md) in the game project. Reuse existing planning material instead of creating a document pack. A read-only review does not authorize state migration or documentation writes.

## Agree the implementation package

For new games and existing-project development without an approved contract, run the bundled [game-planning workflow](references/game-planning.md). It owns the interview rounds and planning handoff; it requires no external Wayfinder, grilling skill, installation or separate chat. The lead interviews the actual owner in this chat. Read the [question bank](references/interview-topics.md) during planning and the [package format](references/implementation-package.md) when recording the agreement and preparing tickets.

Deliver a versioned contract, an explicit milestone roadmap, related scoped implementation tickets with execution prompts, and a readiness handoff. Ask rounds of related, currently answerable questions, recommend answers, wait for the owner's responses, and recompute dependencies. Never answer for the owner or treat recommendations as decisions. Record decisions as they settle; draft planning artifacts are allowed within authorized scope, game implementation and asset production await contract approval.

Contract approval replaces the former concept gate. Art and slice approvals remain. Provisional choices must name a bounded experiment, its acceptance criteria and the work it blocks; do not freeze choices that need visual or play evidence. Fully specify executable near-term tickets and keep later work blocked where prerequisites remain unknown.

For a focused fix under an existing contract, use its ticket or a small amendment; do not restart accepted planning. A legacy project with no contract needs only an owner-approved agreement covering the requested change and affected baseline, not a retrospective whole-game redesign. Report-only reviews do not require a new contract. Preserve valid previous approvals and use [state migration guidance](references/state.md) when resuming older runs.

## Coordinate the specialists

Spawn bounded tasks using the appropriate role reference:

- [Designer](references/designer.md): planning support, rules, progression and tuning.
- [Artist](references/artist.md): representative art, coherent assets and measured handoff.
- [Developer](references/developer.md): engine feasibility, implementation, integration and packaging.
- [Tester](references/tester.md): independent checks of the actual build against the approved experience.

Before each dispatch, check the current contract revision, ticket dependencies, applicable approvals, blockers and latest owner messages. Give each subagent the relevant contract requirements, exact ticket and role-reference paths, game workspace, relevant files, expected output, permitted writes and a stopping condition. Include the current gate/blocker and instruction to report back rather than approve itself. Load relevant references only. Specialists may recommend amendments; only the lead reconciles them with owner approval. Prompts do not override gates or expand permissions.

Assign non-overlapping file ownership; the developer owns final integration. Parallelize independent work only, within available concurrency. Keep one shared remaining-work list. The lead alone writes the state record and dispatches the next stage. Specialists do not recursively expand the team or edit the engine, publish, or post issues on their own. If subagents or necessary tools are unavailable, report the limitation and pause affected work instead of pretending a team ran.

## Progress through three approvals

1. **Contract:** after the interview, present the exact implementation package revision, essential requirements, exclusions, provisional choices and first executable milestone. Developer checks material engine/platform risks through read-only feasibility inspection. Record `AWAITING_CONTRACT_APPROVAL` and wait before asset production or game implementation. The owner approves that revision; interview answers alone do not approve the package. For a planning-only request, deliver the package and stop; approval does not authorize implementation outside the request.
2. **Art:** after contract approval and authorization to build, create the agreed small representative scene or asset set at intended display scale, showing animation when it matters. Developer may build only the bounded feasibility work and minimal preview scaffolding authorized for this milestone. Present actual candidate art, not just prose or a moodboard. Resolve the contract's relevant provisional choices with that evidence. Record `AWAITING_ART_APPROVAL`; do not expand the asset set or build the full slice until approved.
3. **Slice:** after art approval, execute the slice tickets to integrate one small complete play segment with real assets, controls, feedback, UI and audio where relevant. Include outcome and retry/continuation. Tester exercises its contract criteria and remaining provisional gameplay choices; fix material failures before presenting a launch command or runnable artifact. Record `AWAITING_SLICE_APPROVAL`. Owner approval must follow their opportunity to play; automated success is not human acceptance.

At each gate, identify exactly which artifact/build is being approved, ask for that approval, save state, then end the turn. Silence, elapsed time, a specialist's verdict, or approval of a previous stage is not approval. On rejection, revise the affected part and preserve still-valid work. If scope or acceptance changes, propose a contract amendment and stop affected dispatch until approved; reopen affected art/slice approvals only when their experience changes. Routine fixes and ticket elaboration within approved requirements do not need repeated approval.

## Produce and deliver

After slice approval, execute the remaining agreed tickets autonomously in small playable increments. Reuse approved art and the proven asset pipeline. Update the roadmap as dependencies resolve; never execute a blocked outline. Prefer simplification within the contract over new infrastructure; do not silently cut requirements. After repeated failure without new evidence, choose a simpler permitted approach or report the concrete blocker instead of cycling indefinitely.

For missing engine capability or a suspected engine defect, follow [engine blockers](references/engine-blockers.md). Record `BLOCKED_ENGINE` and stop dependent dispatch. No workaround may silently bypass a required engine exercise. Missing tools or other external dependencies use `BLOCKED_EXTERNAL`, not an invented engine failure.

Run applicable project checks plus focused checks of changed behavior. Reuse unaffected evidence. The tester checks contract acceptance criteria, the delivered entry point and required play paths, including persistence only when included. Link ticket and final evidence to requirement IDs. Keep automated results, observed runtime behavior and human approval distinct. Do not report completion with missing essential target/runtime evidence, unresolved required provisional choices or unmet requirements.

Deliver a complete local browser build with local serving instructions for web, or a runnable application for the agreed desktop OS. A browser dev server alone is not a desktop deliverable. Include source, required assets, applicable credits, and exact build/launch commands. Set `COMPLETE` only when the agreed scope works and the artifact is available. Freeze additions. Publishing is out of scope for this version.

After game completion, write `GAMEDEV-REPORT.md` in the game project following [the final-report guidance](references/final-report.md). Reuse delivery evidence and actual development friction; do not reopen the game or add a review gate. Record the report under state artifacts, link it in the concise final handoff, and stop.
