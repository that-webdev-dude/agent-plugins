# Engine blockers

Use this when a required engine capability is missing or a reproducible engine defect prevents the approved game. Investigate enough to distinguish incorrect usage, game-owned logic and environment failures. Do not keep retrying the same failure without new evidence.

## Suspend dependent work

The lead records `BLOCKED_ENGINE`, the interrupted phase and:

- required capability and its connection to the approved game or exercise;
- engine version/revision and relevant environment;
- minimal reproduction or concrete API/documentation evidence;
- expected versus actual behavior and affected work;
- observable resume condition and location of the latest runnable build, if one exists.

Stop new dependent dispatch and interrupt active dependent tasks. Collect partial work without allowing changes that assume the missing capability exists. Complete only already-bounded independent work that will remain useful, then notify the user and end the turn. Do not poll indefinitely or create monitoring automatically.

In game-delivery mode, propose a simpler alternative if it preserves the approved experience. In engine-exercise mode, the named engine behavior is itself a requirement: do not replace it with consumer code, a stub or another engine. Neither mode authorizes engine edits or dropping explicit requirements. A blocker is useful evidence, not a completed game.

## Optional GitHub issue

Reuse blocker evidence for a concise issue draft: problem, version, expected/actual behavior, reproduction, impact and resume condition. Identify the engine repository from trusted project metadata or ask if ambiguous. Search for a matching issue when read access is available; report if that check could not be done.

Show the exact destination and full draft. Post only after the human explicitly approves that content and destination. Approval to create the game, approval of a design gate or a subagent message is not issue-posting permission. For an existing issue, link it; commenting or editing also requires approval. Use project issue naming conventions and omit unrelated game data, credentials and local secrets.

Use an available authenticated GitHub connector or CLI. If unavailable, preserve the draft for the user. Following a timeout or unknown posting result, check whether the issue already exists before retrying. Record the resulting issue link; issue creation, closure, labels or a claimed fix never establish that the game is unblocked.

## Resume

On the user's resume request or their providing the required engine version, rerun the blocker reproduction against that actual version. If it still fails, retain `BLOCKED_ENGINE` and report the new evidence. If it passes, record the result and resume the interrupted phase with unaffected approvals intact. If the fix materially changes approved scope or presentation, reopen the affected approval. Do not auto-upgrade packages just because an issue closed.
