---
name: neon-wallpaper
description: Simplify a user-provided photo into a minimal 1980s–1990s neon wallpaper with flat color blocks, clean silhouettes, sparse detail, and a limited blue-coral palette. Use when the user wants a photo reduced and redrawn as a retro poster, blue-hour apartment, coral sunset city, midnight arcade wallpaper, or looping-wallpaper source image rather than merely recolored or filtered.
---

# Neon Wallpaper

## Overview

Turn one supplied photo into a simplified desktop wallpaper with the blue-and-coral neon mood established by the local NEON STILL prototype. Reconstruct the photo as graphic shapes instead of preserving photographic complexity. Use the built-in image generation tool; do not require or expose an API key.

## Workflow

1. Confirm the supplied image is the edit target. If it is only a style reference, generate a new scene instead.
2. Ask only for missing essentials: scene preset, intended desktop aspect ratio, and whether a person or object must remain recognizable. Default to `blue-hour-apartment`, 16:9, and preserve only the subject's identity, silhouette, pose, and key proportions.
3. Analyze before generating. Reduce the input to: one dominant subject, two or three depth layers, three to five large color regions, and at most three supporting objects. Ignore incidental clutter.
4. Use the image generation tool in edit mode. Rebuild the scene as a minimal flat poster; do not apply a neon filter to the original pixels.
5. Produce one wallpaper at a time. For a requested animation, generate a strong still source image first; describe optional motion as a later video-generation step rather than claiming the still is animated.
6. Run the simplification gate below. If the output remains busy, edit the generated result once more and explicitly remove 40–60% of the remaining small shapes and texture.
7. Save the selected final image in `generated/` under the current project. Create the directory if necessary. Name files descriptively, such as `neon-blue-hour-minimal-01.png`.

## Simplification Gate

Treat these as hard constraints unless the user requests more detail.

- Use 3–5 dominant colors. Favor deep navy and cobalt for 70–85% of the image, with coral, vermilion, or warm peach as the accent.
- Organize the scene into 2–3 depth layers: dark foreground silhouette, simplified middle subject, broad sky or background plane.
- Replace texture with shape: foliage becomes one or two canopy silhouettes; buildings become clean blocks; windows become sparse dots or short lines; furniture becomes geometric masses.
- Keep only 1 focal element and no more than 3 secondary objects. Remove decorative objects, cables, tiny props, dense signage, repeated windows, and background clutter.
- Prefer solid fills, hard-edged shadows, clean contours, and long geometric light shapes. Allow at most one subtle sky gradient.
- Preserve the original composition and subject hierarchy, not every surface, pattern, reflection, leaf, hair strand, or material detail.
- If a person is present, preserve face shape, hairstyle silhouette, pose, and clothing color blocks; simplify facial detail without turning the person into an unrelated character.
- Reserve at least 25% calm negative space for desktop icons or clock widgets.

Reject an output as too complex when it contains photoreal textures, many small objects, dense foliage, hundreds of lit windows, intricate reflections, fine fabric or hair detail, cinematic particles, or multiple competing focal points.

## Presets

Choose exactly one unless the user asks for variants.

- `blue-hour-apartment`: Broad cobalt sky, one coral horizon band, a simplified skyline, and two or three dark geometric interior silhouettes around a tall window.
- `last-light-city`: Indigo city blocks, one distinct orange-red sun, long hard-edged shadows, and a sparse large-window or balcony composition.
- `midnight-arcade`: Electric violet, cobalt, and coral light reduced to a few sign-like rectangles and simplified reflections; keep the scene graphic rather than busy.

## Prompt Shape

Use a compact production brief. State the input photo's role and all invariants explicitly.

```text
Use case: style-transfer
Asset type: desktop wallpaper
Input image: supplied photo is the edit target
Primary request: Simplify and redraw it as a minimal <preset> 1980s–1990s neon wallpaper. Reconstruct the scene with flat graphic shapes; do not merely recolor or filter the photo.
Scene/backdrop: <preset scene>, reduced to 2–3 depth layers and no more than 3 supporting objects.
Style/medium: minimalist retro-futurist poster illustration; clean vector-like silhouettes; large flat color blocks; hard-edged shadows; restrained geometric detail.
Palette: 3–5 colors total; deep navy and cobalt dominate; coral, vermilion, or warm peach are used only as accents.
Composition/framing: <ratio>; preserve the source's main composition and subject hierarchy; reserve at least 25% calm negative space for desktop icons.
Constraints: preserve <subject identity, silhouette, pose, and key proportions>; simplify or remove micro-detail, texture, clutter, dense windows, individual leaves, reflections, fabric detail, and decorative props.
Avoid: photorealism, painterly texture, complex lighting, intricate material rendering, fine grain, bloom, particles, extra objects, logos, watermark, captions, UI elements, and illegible text.
```

## Output and Limits

Return the saved local file path, the prompt used, and a one-line simplification summary listing what was retained and removed. Do not claim that the image has been set as the operating system wallpaper. Do not use a browser-facing API key or attempt to make the local web prototype call this skill; the skill runs inside Codex for personal use.
