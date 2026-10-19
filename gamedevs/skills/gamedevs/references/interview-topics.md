# Interview topics

Use as a coverage bank for [game-planning rounds](game-planning.md), not a script to recite. Select related questions whose dependencies are settled, recommend answers and wait for the owner. Inspect technical facts first. Reuse supplied answers and existing approved decisions. Record irrelevant topics as not applicable; ask pixel-art-specific questions only for pixel-art projects. Production specifications can remain provisional pending an approved sample.

The art topics adapt the owner's supplied 15-part art-commission interview; gameplay, audio, implementation and acceptance topics extend it to a complete game agreement.

## Experience and audience

- What does the player do during a typical minute? What setting, premise, central fantasy and distinctive mechanic should define the game?
- What emotions and visual character should it create? Who is the audience, and what content or age-rating boundaries apply?
- Is success a complete small game, a change to an existing game, or proof of named engine capabilities? What existing behavior and assets must remain?

## Rules, controls and run structure

- What are the player's actions and input devices? What makes those actions responsive and understandable?
- What are the goals, success/failure outcomes and retry/continuation rules? How long should a session take?
- What challenge, pacing, difficulty, progression, content variety or replayability is essential? Which counts or tuning choices need play evidence?
- Are saves, settings persistence, procedural generation, multiplayer, accounts or online services required, excluded or undecided? Explore their consequences only when included.

## Platforms and display

- What engine and web/desktop target, launch devices and desktop OS are required? What runtime support can current evidence establish?
- Will people use monitors, televisions, handhelds or phones? Which orientations, aspect ratios, window sizes, resizing and fullscreen modes must work?
- What minimum supported display/window and reference hardware should define acceptance? What performance, memory and download-size limits apply, and how will they be measured?

## Scope and resources

- Which assets, code and documents exist, and which must be created, replaced or preserved?
- What characters, enemies, bosses, locations, objects, effects, screens and other content are included? Distinguish first playable, final required content and optional ideas.
- Does the work include concept art, production assets, animation, UI, audio, logos or promotional material? Who handles integration, lighting, layout and final adjustments?
- What budget, tool/generation limits, deadline, milestones and revision allowance actually apply? Recommend bounded experiments rather than inventing allowances.

## Visual references

- Which games, illustrations, films or artists are references, and what specifically should carry over: silhouettes, colour, materials, motion, composition or atmosphere?
- Which styles should be avoided, and why? Is historical hardware fidelity relevant?
- Should the work feel restrained, ornate, playful, realistic or exaggerated? Which existing brand rules or recognisable designs must survive?

## Camera and composition

- What perspective and camera behavior are intended: fixed, scrolling, following, zooming, rotating or changing between scenes?
- How much surrounding space must remain visible? How large should the player, ordinary enemies and bosses appear relative to the screen and each other?
- Where must composition leave room for HUD, warnings, dialogue and interaction prompts?

## Resolution and scale

- Is native resolution established, or should the art experiment compare candidates? What details must remain visible on the smallest important assets?
- For pixel art, what sprite dimensions and shared pixel grid support that detail? Should world, backgrounds, effects and UI share the grid?
- How should different displays scale the image: integer enlargement, borders, cropping or expanded view? Are close-ups, alternative zoom levels or higher-resolution UI required?

## Palette and readability

- Is a palette established, strictly limited or coordinated? Should levels have distinct palettes with common colours?
- Which colours identify the player, enemies, factions, hazards, rewards and interactions? How should foreground brightness and saturation differ from backgrounds?
- Which distinctions must also work through silhouettes, symbols, motion or text rather than colour alone?

## Shapes, materials and lighting

- What silhouette language, proportions, perspective, outlines and detail density should remain consistent?
- Which materials need distinct treatments? Is lighting painted into assets, applied at runtime or combined, and what direction/intensity applies?
- Are shadows, reflections, glow, emission masks or normal maps needed, and does the verified pipeline support them?

## Environments

- Which locations, biomes, visual themes and alternative states are required? Are transitions, weather or time-of-day changes included?
- Are scenes built from tiles, modular pieces, large backgrounds or a mixture? What tile dimensions, connection rules and seamless repetition are needed?
- Which foreground, gameplay, background and parallax layers are needed? What is interactive, destructible, animated or decorative, and where must the scene remain visually quiet?

## Characters and objects

- What gameplay role and immediately recognisable information does each asset communicate: strength, speed, faction, vulnerability or function?
- Which upgrades, equipment, damage states, skins, directions and viewing angles are required? Which components are separate or interchangeable?
- What frame bounds, visible artwork size, anchors and attachment points are needed? What collision or interaction boundaries should the art communicate?

## Animation

- Which states and transitions are required, and what should motion feel like: sharp, heavy, fluid, mechanical or elastic?
- What duration, frame count or production budget applies? Which clips loop, which play once, and which gameplay events align with frames?
- Can frames be mirrored despite asymmetry? What must stay anchored between frames to prevent unintended movement?

## Effects and feedback

- Which actions need effects, and what must they communicate? Which belong in sprites, particles, shaders or combinations?
- Which blending/transparency treatments are supported? How much screen coverage, intensity, layering and timing preserve readability during busy play?
- Are reduced-motion, reduced-flash, camera-shake or similar alternatives required? Which effects must align with attachment points or gameplay events?

## Audio

- Which music, ambience, action cues and UI sounds are essential, and what must they communicate?
- What sources, licences, tools, volume controls, muting and playback constraints apply?
- Which important audio cues also need visual equivalents? How will actual playback be checked on the target runtime?

## Interface and supporting artwork

- Which menus, HUD elements, icons, cursors, portraits, dialogue and results screens are included? What must be readable during action at minimum display size?
- Does UI share the world's resolution? What licensed fonts, languages, text expansion and keyboard/controller/touch prompts are required?
- What selected, disabled, pressed and focused states must controls communicate? Are logos, store images, screenshots, trailers or promotional illustrations included?

## Technical asset delivery

- Which verified engine/editor/pipeline consumes the files? What source/export formats, individual frames, sheets or atlases are required?
- What naming, folders, animation tags, frame rectangles, timing, pivots and attachment metadata apply?
- What trimming, padding, atlas borders, texture dimensions and compression constraints apply? Are layered sources, palettes, tilemaps or editable animation files required?
- How will exports be previewed in the actual game, including animation playback and repeated tiles where relevant?

## Ownership, approval and completion

- What usage/ownership rights, editable sources, third-party assets, stock, generative AI and production tools are permitted? What attribution, confidentiality, portfolio and release restrictions apply?
- Who gives final approval and consolidates feedback? Which representative sample and playable segment must be approved before expansion?
- What observable criteria establish readability, consistency, behavior, technical validity and delivery? Which require automated checks, runtime observation or owner play?
- What local build, source, assets, credits and launch instructions constitute delivery? What actions are authorized, and which need separate permission?
- How should changes to approved scope, style, asset counts or resolution be handled? Which open choices require a bounded experiment and what work must wait for its result?
