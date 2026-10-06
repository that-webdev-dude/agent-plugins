# Small tile sets

Use this note for repeated terrain and connecting edges.

- Begin with a master fill that repeats on the required edges. Check a multi-tile patch, not just an isolated square.
- Make deliberate edge and corner pieces when two materials meet. The required variants depend on the game's adjacency rules; do not invent a full autotile system for a small art request.
- Keep texture scale, palette and light direction shared with the sprites. Reduce strong isolated marks that expose the grid when repeated.
- Add a quiet variant to break repetition, while keeping connection boundaries compatible.
- Preview intended combinations at game size. Measure edge pixels when exact wrap is required, but also inspect repeated texture: matching borders alone does not prove attractive tiling.

Original visual: [Tiles1x.gif](visuals/Tiles1x.gif), covering the master tile, edge construction and variation.

Paraphrased from Pedro Medeiros / Saint11. See [attribution](ATTRIBUTION.md). The adjacency and handoff advice above is this pilot's practical application, not a quoted engine API.
