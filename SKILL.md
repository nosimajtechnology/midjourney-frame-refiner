---
name: midjourney-frame-refiner
description: Refine supplied Midjourney frames or other generated stills into cleaner production frames while preserving identity, composition, lighting, and visual style. Use for cleanup, muddy SD generations, artifact removal, faithful image refinement, and optional upscaling before animation in Big Bridge or Nosimaj Studio. Especially protect intentional PS1/PS2 geometry, painted textures, anime linework, and atmospheric softness.
---

# Midjourney Frame Refiner

Turn a supplied frame into a cleaner version of itself. Treat the source image as visual authority. Default to the conservative restoration that improves readability without redesigning the scene.

## Inputs and defaults

Require a viewable source frame; accept an attachment, local file, or existing project asset. Inspect it before editing. If unavailable, request the source rather than inventing it.

Default to one balanced refinement, original aspect ratio and framing, and source style preserved. Execute when an image-editing capability is available. Do not ask an intake questionnaire. Accept optional strength (light/balanced/strong), target size, specific repairs, and protected details. Interpret “SD” as standard definition unless the user establishes another meaning.

- Light: reduce incidental noise and blur with minimal reconstructed detail.
- Balanced: clean obvious degradation and clarify existing facial features, fabric, materials, and edges. Use this by default.
- Strong: more reconstruction only on explicit request; keep the same visual identity.
- Upscale only: avoid generative redesign. Use an available dedicated upscale workflow consistent with runtime instructions; if unavailable, explain the limitation.

Do not impose PS2 styling on anime, photography, or other sources. Infer medium from the supplied image.

## Workflow

1. Inspect the actual image. Record source dimensions when accessible. Identify subject, expression, silhouette, pose, crop, camera angle, object layout, palette, light direction, texture language, and intentionally rough stylistic features.
2. Separate degradation from style. Target compression blocks, excessive canvas-like noise, smeared contours, muddy eyes, and unclear material edges. Preserve intended low-poly geometry, texture wobble, painted shading, cel lines, bloom, haze, film grain, and darkness. Reduce only the distracting excess.
3. Build a short source-specific edit prompt using the template below. Name visible invariants precisely. Never add character canon absent from the source: no added white hair, ears, tails, crowns, logos, wardrobe, or scenery just because a character engine normally expects them. Apply explicit user changes as exceptions.
4. Send the original as the edit target to an actual image-editing tool. Prefer the built-in image generation/editing tool when available; obey its image-input and output handling instructions. In Big Bridge, inspect the project's existing instructions and image-edit provider adapter, then use its configured image-to-image route. Do not invent an endpoint, command, model identifier, strength parameter, or API key setup. Do not convert this to text-to-image.
5. Request the source aspect ratio and an appropriate supported output size. Treat requested dimensions as a target until verified. For exact 2x/4K or a requested delivery size, verify the returned pixel dimensions and use an existing permitted upscale route if necessary. Do not label a refinement as a verified 2x upscale on prompt wording alone.
6. Compare the output with the source at whole-frame and detail scale. Check identity/expression, crop, object count/placement, pose, costume, light, color, and medium. Ensure cleaner eyes and materials do not become glossy modern CGI, synthetic fur, excessive microtexture, sharpened halos, or erased atmosphere.
7. If there is a clear defect, make at most one focused corrective attempt using the original plus the candidate as supported by the tool. Explicitly name the defect. Avoid repeated generation chains that accumulate drift. If unresolved, report the limitation instead of declaring exact preservation.
8. Preserve the original. Save the selected result as a distinct project asset using existing project conventions, such as `<source-stem>-refined-v01.png`. Follow the host's saving and display rules. Return the image and one brief sentence about the changes. Report actual dimensions only if verified.

## Prompt template

Fill the brackets from observation; do not send placeholders.

> Edit target: the supplied image. Perform faithful [light/balanced/strong] cleanup and refinement of this exact frame.
> Preserve: [specific subject identity, face/eyes/expression, proportions, pose, costume, objects, framing, background, lighting, palette].
> Medium: [observed visual language]. Retain [intentional geometry, texture, linework, softness, grain or haze].
> Improve only: [observed noise, blur, compression, muddy details, unclear material highlights]. Clarify existing edges and readable forms conservatively.
> Constraints: no redesign, added objects, changed expression, new costume details, crop, camera change, or reinterpretation. Do not modernize the rendering or invent intricate detail absent from the source. Preserve the original aspect ratio.
> Output: [supported size target, if known]. Restoration of the supplied image, not a new rendition.

For PS1/PS2 sources, add: “Keep simple game geometry and painted textures. Do not convert to modern AAA graphics, photorealistic fur, or a polished cartoon illustration.”

For cel anime, add: “Keep line weight, flat color regions, cel shadows, and period-specific softness. Do not add 3D shading or modern digital gloss.”

## Big Bridge handoff

Use this as a step between the chosen Midjourney genesis frame and storyboard/animation preparation. Return the selected refined asset to the existing pipeline; do not automatically animate, replace a project's approved frame, rewrite a character engine, or change provider configuration.

When installing into a local checkout, inspect AGENTS.md and the project's existing skill discovery conventions. Copy this skill folder into the matching skill directory; register it only if the project requires registration. Verify discovery with the project's documented mechanism. Avoid asserting that a ChatGPT skill installation also installs it into a local Big Bridge checkout.

When no image-edit provider is available, provide the ready-to-run edit prompt and state that execution needs an image-editing connection. Do not claim to have refined an image. Keep credentials in the project's existing secure configuration.

## Calibration example

Source: a tan Chihuahua with large glossy black eyes, a pink durag with ties extending left, silver plate armor, and a plain gray-brown background in a soft retro game render.

Successful behavior: reduce the heavy canvas-like grain and blur; clarify eyes, nose, durag folds, armor edges and highlights; preserve expression, pose, framing, muted palette and retro material language.

Failure: add canonical white hair, change the armor design or face proportions, replace the background, add an aura, or transform the frame into photorealistic modern CGI.

Treat this as a behavior example, never as a subject to insert into unrelated frames. Recognize that generative refinement reconstructs details; do not promise pixel-identical preservation.

