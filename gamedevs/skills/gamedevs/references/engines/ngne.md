# NGNE consumer guidance

Inspect the selected package or checkout before using APIs. The source reviewed for this pilot on 2026-10-06 identifies `@ngne/core`, exposes the engine through its public package entry point and includes `ngne-preview`. Those are orientation hints, not proof about another version. Read the installed version's declarations, bundled guide and matching examples. Pin the chosen version; do not silently upgrade or import the engine's private source.

NGNE's reviewed README assigns application setup, assets and game logic such as movement, collision and progression to the consumer. Check the selected version's actual contract before calling a missing game feature an engine blocker. If the user explicitly wants to exercise an engine capability, verify that exact path rather than substituting consumer behavior.

For a new web consumer, use the project's existing setup or a minimal TypeScript application. Verify a tiny scene against the selected engine, then integrate the game's actual assets. Keep browser setup and game rules clearly separated where useful. Do not create a generic framework or migrate the engine as part of building a game.

The reviewed README uses WebGPU, localhost or HTTPS, and a capable browser. Verify the actual target runtime. For desktop, establish the application wrapper, packaging and WebGPU support for the selected OS before promising delivery; do not assume the engine includes a desktop exporter.

Read the consumer's package scripts for build, tests and preview. Use `npm.cmd` in Windows PowerShell. If `ngne-preview` is available in the selected version, use its documented config and measured frame metadata for targeted asset checks; it supplements the real game scene. Neither a valid atlas nor a preview screenshot establishes human art acceptance.

The bundled pixel-art guide is intentionally engine-neutral. Do not force a particular Pixel Artist export package or infer loader APIs from it. Reuse a validated consumer export workflow if already available.

Reference locations, to inspect only when needed:
- [Engine repository](https://github.com/that-webdev-dude/ngne)
- Installed package's `docs/guide.md` and declarations, or the matching selected checkout.
