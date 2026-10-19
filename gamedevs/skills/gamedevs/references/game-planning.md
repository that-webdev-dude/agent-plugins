# Game planning

Run this internal workflow through the gamedevs lead, in the owner's current chat. It is managed and versioned with the plugin, not a separately invoked skill or background interview. It adapts Wayfinder's destination, decision dependencies and progressive discovery, and grilling's question rounds. It has no external Wayfinder, grilling, domain-modeling, tracker or installation prerequisite. Do not load those skills or inherit their explicit-invocation or one-ticket-per-session restrictions.

## Establish the baseline

Read project instructions, existing plans, state, source, assets and available build/runtime evidence before asking what is already discoverable. For a new game, establish its destination: the intended experience and local deliverable. For an existing game, identify what is being preserved, changed and excluded. Distinguish owner statements, verified facts, proposals and unknowns. Existing code does not automatically express an approved requirement.

Keep the owner's engine and target as choices they make. Recommend feasible options when they are missing. Verify engine/version, tooling, platform and asset-pipeline facts through inspection; do not ask the owner to discover them for you. Delegate bounded fact-finding to a specialist where useful, with no game implementation or production assets. A running investigation blocks only questions that depend on its result.

Use the [question bank](interview-topics.md) to check coverage. Existing answers remove questions; irrelevant topics are marked not applicable with a short reason. Do not prescribe pixel art, networking, saves, a content count, a budget or a deadline when none was agreed. Explain technical choices in terms of visible consequences and offer a recommendation.

## Interview in rounds

Model the interview as a decision tree. Its frontier contains the unresolved questions whose prerequisites are settled. Start breadth-first across the game experience, scope, audience, target and constraints, then deepen the branches as answers unlock them.

The interview is the requested planning work, not a preliminary clarification before doing that work. Use related-question rounds by default; do not interpret a general preference for concise clarification as a request to serialize the interview. An express owner instruction about interview format takes precedence.

1. Select a coherent round of related questions from the current frontier. Ask all currently answerable questions for that topic together. Do not drip-feed one question per turn, and do not dump the entire question bank into the first round. Use as many questions as the related decision set needs; a single question is appropriate only when it is genuinely the only remaining answerable decision or the owner explicitly requests it.
2. Number the questions and give a recommended answer or useful options with their consequences. Recommendations are proposals, never recorded owner decisions. Keep question numbers unique within a round and identify the round when resuming it.
3. Present the entire round together, record its pending questions and set `AWAITING_INTERVIEW_ANSWERS`. Wait for the actual owner's responses before moving to a dependent round. If a question interface would serialize them into separate turns, present the numbered batch together in chat instead.
4. Reconcile answers, resolve contradictions and record the resulting decisions immediately within authorized documentation scope. Preserve the owner's words or an attributable summary and the affected requirement/decision IDs. If an answer covers several questions, use it once; if only part of a round is answered, retain the unanswered questions and ask them together with newly unblocked related questions. Never invent the rest of the answers.
5. Recompute dependencies and ask the next related round. Work may continue across several rounds in the same chat; there is no one-decision-per-session rule.

Example round, where the engine and web target are already established:

```text
Round 2 — Run structure and outcomes

Q1. How long should a successful run take?
Recommendation: 5–10 minutes for the first version, so the full loop can be tested quickly.

Q2. What should end a run in failure?
Recommendation: losing all health, followed by a clear result screen and immediate retry.

Q3. What should carry between runs?
Recommendation: nothing initially; record persistent progression as excluded unless it is central to your idea.
```

Do not ask for the precise wave count in this round if it depends on the unanswered run-length decision. A later round can ask about pacing once that prerequisite is settled. The example is a format, not a default game design.

## Record decisions and remaining uncertainty

Reuse established project documents; otherwise use the compact [implementation package](implementation-package.md). The contract is the normative agreement. Keep rationale and a small decision history beside the relevant contract clauses; the roadmap indexes them rather than restating the agreement. Keep domain terms in an existing glossary, or a short contract glossary when terminology needs clarification. Do not generate a separate ADR or design-document collection by default.

Use stable requirement IDs (`R-001`), decision IDs (`D-001`), milestones (`M-01`) and tickets (`T-001`) without recycling retired IDs. Refer to artifacts by descriptive linked titles with their IDs, not bare numbers.

Every question-bank topic is either covered, explicitly excluded/not applicable, or represented by a named unresolved/provisional decision. For unresolved choices, record the question, dependencies, affected work and next resolver. Uncertainty that is not yet precise enough to ticket stays in a short "Not yet specified" list, with the milestone it prevents. It is not silently assumed away or treated as out of scope.

An owner can approve a provisional choice only with a bounded experiment: what to try, resource/scope bounds, what evidence will judge it, who decides, and what stays blocked. Appearance, sprite scale, animation and fun often need the art or slice gate. Draft the agreed target now; approve its actual realization at that gate. If feasibility needs implementation before a wider commitment, make that experiment the only executable milestone under the initial approved contract. Do not implement it during an unapproved interview.

## Assemble and approve

Produce the five outcomes described in the [package format](implementation-package.md): contract, roadmap, scoped tickets, execution prompts and planning handoff. Use existing authoritative documents and combine the handoff into the roadmap when suitable. Even a small effort needs an explicit agreement; it does not need a separate decision map or issue tracker.

Planning is ready for owner review when:

- the experience, included scope, exclusions, engine/target and deliverable are clear;
- each required outcome has observable acceptance criteria and an owner/agent verification responsibility;
- dependencies and approval gates are explicit, with no unresolved decision blocking the first executable milestone;
- provisional choices have bounded resolution work and blocked dependents;
- all agreed scope is mapped to milestones/tickets or an explicit blocked planning item;
- near-term tickets are fully specified, executable once their stated approval gates permit, and their prompts refer to the actual project artifacts;
- action permissions and resource limits are recorded without inventing authorization.

Present the exact package revision and first milestone, highlight remaining provisional choices, set `AWAITING_CONTRACT_APPROVAL`, save state and end the turn. Wait for explicit owner approval of that revision; answering the interview is not package approval. Record approval evidence and artifact identities using [state guidance](state.md). Approval to plan does not authorize implementation; for a planning-only request, stop at handoff until the owner asks to execute.

## Resume and amend

On resume, load the current contract, roadmap, pending round and relevant decisions/tickets. Verify revisions and prerequisites against current files and the owner's latest instructions. Resume the pending round or next ready ticket; do not repeat settled questions or recreate the package. Use [state migration](state.md) for older gamedevs runs.

For existing projects with no contract, propose a baseline from current evidence and confirm it with the owner in rounds. Preserve valid art/slice approvals with their original evidence. For a focused change, agree only its scope, affected baseline, acceptance criteria and execution ticket; reuse unaffected evidence rather than interview the whole game again. A report-only review can remain a report, and a completed legacy run missing only its final report does not need retroactive planning.

When a new request or discovered limitation changes an approved requirement, exclusion, acceptance criterion or material resource limit, present an amendment: affected clauses, rationale, impact, revised tickets and approvals to revisit. Keep the previous approved snapshot, block affected work, and seek approval of the amendment. Preserve independent valid work and approvals. Elaborating a ticket or fixing a defect within the agreement does not itself amend the contract. If approved experiments settle a provisional choice within its authorized bounds, record the evidence at the specified gate; a result outside those bounds requires amendment.

## Execution handoff

After contract approval and authorization to build, the lead dispatches only ready tickets permitted by the current art/slice gate. Each specialist receives the applicable requirements and prompt; only the lead updates shared state and reconciles amendments. Keep the roadmap and ticket evidence current as approved experiments resolve. No ticket, prompt or specialist verdict approves itself or bypasses the contract. Final delivery must account for every required outcome, including provisional choices that were required to be resolved.
