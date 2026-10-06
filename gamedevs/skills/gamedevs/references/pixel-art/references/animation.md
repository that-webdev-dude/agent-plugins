# Character animation

Use this note when making or reviewing a walk/run loop.

- Establish the action with distinct key poses before adding in-betweens. A run needs changing contact, compression/recovery and airborne poses; translating one still sprite is not a run cycle.
- Keep body proportions, clothing shapes and pivot placement consistent. Arms generally counter the legs; avoid accidental changes in identity or lighting between frames.
- Let the torso rise and fall with the action, while intentional planted feet hold their contact. Distinguish purposeful bounce from whole-frame registration jitter.
- Review the wrap from the last pose to the first. Timing and spacing affect weight; choose durations for the movement rather than copying the tutorial's GIF timing as a game requirement.
- Show the actual frames at intended size in a loop. If only stills were inspected, say so. Increase frame count only when it solves a visible motion problem.

Original visual: [RunCycleSimple1x.gif](visuals/RunCycleSimple1x.gif). It demonstrates key poses and in-betweening; its illustrated character is a teaching reference, not the requested game character.

Paraphrased from Pedro Medeiros / Saint11. See [attribution](ATTRIBUTION.md).
