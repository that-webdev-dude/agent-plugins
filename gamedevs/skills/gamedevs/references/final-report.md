# Final gamedev report

The delivery lead writes `GAMEDEV-REPORT.md` in the game project after successful completion. Keep it short and reuse existing handoffs, code and verification evidence. Update an existing report rather than creating duplicates. If an otherwise completed run only lacks its report, write it from existing evidence and retain `COMPLETE`; do not restart production.

## Delivery

Summarize the delivered game, adopted engine and exact version/revision, target, artifact and launch instructions, actual verification and material limitations. Distinguish automated checks, observed runtime behavior and human approval. Reference existing evidence instead of repeating logs or rerunning tests.

## Optional engine improvements

List only non-blocking development conveniences that the team actually missed while building this game, from repetitive helpers to larger capabilities. Include a candidate only when all three apply:

- **Observed friction:** existing code or task evidence shows repetition, a workaround or substantial integration effort. Cite the relevant path or task and describe what was needed.
- **Broad reuse:** the capability plausibly helps different games or genres independently of this game's rules, content and presentation. Explain that reuse; one game's evidence is provisional, not proof of cross-game demand.
- **Missing in the adopted version:** check the relevant public APIs and documentation before claiming an absence. Keep this check focused on the observed need. If absence cannot be established, omit the candidate rather than guessing.

For each qualifying candidate, record:

| Candidate | Observed friction and evidence | Reuse and expected benefit | Likely home |
| --- | --- | --- | --- |
| Generic capability or helper | What was implemented and where; relevant API/doc check | Why other games could use it and what repeated work it could reduce | Engine core, optional tooling/helper, or documentation |

If the capability already exists and discoverability caused the friction, label it documentation feedback rather than a missing engine feature. Broad usefulness alone does not justify adding something to engine core. Exclude game-specific enemy behavior, scoring, progression, content, speculative wishlist items and unresolved delivery blockers.

There is no candidate quota. Write **No qualifying candidates found** when appropriate. Do not invent time, token or cost savings; use qualitative benefits unless measurements already exist.

Report generation does not trigger new tests, specialist review rounds, engine changes, GitHub issues or another user approval gate. The report is input for later evaluation, not an approved engine roadmap. Genuine blockers still follow the existing blocker workflow and cannot be hidden here as optional improvements.
