# Asset delivery

Use the consumer's existing convention if available. Do not infer NGNE APIs or change the engine to accommodate an unverified image.

For a standalone candidate, provide the original PNG plus plain metadata: image dimensions, frame rectangles in source pixels, ordered frame names, frame durations in milliseconds, pivot convention and tile dimensions. Identify whether coordinates were measured or merely requested. Metadata is a handoff description, not an NGNE loader contract.

Check only what matters to the asset:
- Actual dimensions and cell bounds; no clipped or overlapping artwork.
- Alpha behaviour: transparent backgrounds for characters, intended opacity for terrain. Report partial alpha if the brief requires hard edges.
- Unique poses and consistent alignment; loop timing.
- Tile seams and material consistency in repeated combinations.

Keep three outcomes separate: technical file checks, visual judgment, and actual engine playback. A clean PNG or valid atlas does not establish animation quality. If generation misses the native grid or layout, retain it as a candidate and name the defect rather than silently treating it as a finished sprite sheet.

This delivery guidance is authored for the pilot; the accompanying tutorials do not define NGNE's API.
