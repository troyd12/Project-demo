---
name: image-styler
description: "Generate ready-to-use image editing prompts with adjustable placeholder values for visual effects like gradient transparency (left-to-right fade), drop shadow glow, blur (gaussian/radial/motion/depth-of-field), and combinations of all three. Trigger when the user says anything like 'image effect prompt', 'fade prompt', 'glow prompt', 'blur prompt', 'make me a prompt for image effects', 'image styler', 'gradient transparency prompt', 'drop shadow prompt', 'image editing prompt template', 'visual effects prompt', or wants reusable prompt templates for AI image generators (ChatGPT/DALL-E, Midjourney, etc.). Also trigger when the user mentions adjusting shading, transparency, glow, blur, or drop shadow on an image and wants a prompt rather than direct code edits."
---

# Image Styler — Visual Effects Prompt Generator

Generate copy-paste-ready prompts for AI image generators (ChatGPT/DALL-E, Midjourney, Stable Diffusion, etc.) with adjustable placeholder values for common visual effects.

## When This Skill Is Used

The user wants a reusable prompt template — not a direct code edit — for one or more of these image effects:

- **Gradient transparency** (directional fade from visible to transparent)
- **Drop shadow / glow** (ambient light, colored halos, neon edges)
- **Blur** (gaussian, radial, motion, depth-of-field)
- **Combined / layered effects** (all of the above stacked together)

## How to Respond

### 1. Ask which effects they need

If the user hasn't specified, ask which of the four categories they want (or "all"). Don't assume — people often only need one.

### 2. Generate the prompt(s)

Each prompt must follow these rules:

- **Placeholders use `___` with a label next to them** so the user knows what value goes there. Example: `___% (opacity)` or `___ (color hex)`
- **Group related placeholders together** so the user can see at a glance what to fill in
- **Include a brief parenthetical hint** after each placeholder showing a sensible default or range. Example: `___% (start fade, e.g. 55%)`
- **End every prompt with a background color line** defaulting to black `#0A0A0A` but written as a placeholder so the user can change it
- **Keep prompts self-contained** — each one should work if pasted directly into ChatGPT, Midjourney, or any image generation tool with no extra context needed

### 3. The Four Prompt Templates

Always present prompts in this order when generating multiple. Use the exact structure below, but feel free to adjust wording to match the user's specific image or context if they've described one.

---

#### GRADIENT TRANSPARENCY (Directional Fade)

```
Edit this image to apply a smooth gradient fade from ___ (direction, e.g. left to right / top to bottom / center outward).

Keep the ___ (visible side, e.g. left) side at ___% (opacity, e.g. 100%) opacity — fully visible.
Begin the fade at ___% (fade start point, e.g. 55%) of the image width/height.
Reach full transparency at ___% (fade end point, e.g. 95%) of the image width/height.

The background revealed behind the fade should be solid ___ (background color, e.g. #0A0A0A).
Preserve all original detail, color, and lighting on the visible portion.
```

#### DROP SHADOW / GLOW

```
Add a soft glowing drop shadow around the subject in this image.

Glow color: ___ (hex color, e.g. #C8F900 volt green / #FFFFFF white / #00BFFF electric blue)
Glow intensity/opacity: ___% (e.g. 60%)
Glow spread/radius: ___px (e.g. 40px)
Glow offset X: ___px (e.g. 0px), Y: ___px (e.g. 0px)

The glow should feel ___ (style, e.g. ambient and natural / neon and sharp / soft halo).
Do not add a hard outline — keep it diffused.
Background should remain solid ___ (background color, e.g. #0A0A0A).
```

#### BLUR EFFECT

```
Apply a ___ (blur type: gaussian / radial / motion / depth-of-field) blur effect to this image.

Blur strength/radius: ___px (e.g. 8px)
Blur area: ___ (e.g. background only / edges only / right 40% of image / everything except the subject)
Subject sharpness: ___% (e.g. 100% — fully sharp)
Transition style: ___ (e.g. smooth gradient / hard cutoff / feathered edge)

Preserve the focal subject at full clarity unless otherwise specified.
Background should remain solid ___ (background color, e.g. #0A0A0A).
```

#### COMBINED (All Three Layered)

```
Edit this image with these three layered effects, applied in this order:

1. BLUR
   Type: ___ (gaussian / radial / motion / depth-of-field)
   Radius: ___px (e.g. 8px)
   Applied to: ___ (e.g. background only / edges / right side)
   Subject sharpness: ___% (e.g. 100%)

2. DROP SHADOW / GLOW
   Color: ___ (hex, e.g. #C8F900)
   Opacity: ___% (e.g. 60%)
   Spread: ___px (e.g. 40px)
   Offset: ___px X / ___px Y (e.g. 0px / 0px)
   Style: ___ (ambient / neon / soft halo)

3. GRADIENT TRANSPARENCY (applied last, on top)
   Direction: ___ (e.g. left to right)
   Fully visible: ___ side at ___% opacity
   Fade starts: ___% of image width/height
   Fade ends: ___% of image width/height

Background behind all effects: solid ___ (e.g. #0A0A0A).
Stack order matters — blur first, then glow, then fade on top.
```

---

### 4. Offer to apply directly

After presenting the prompt(s), always offer: "Want me to apply any of these effects directly to your image right now using Python? I can do gradient fades, glow, and blur with PIL/Pillow — same result, no need for an external image generator."

If the user says yes, use Python with Pillow to apply the effect. The gradient transparency effect uses an alpha mask, the glow uses a gaussian-blurred colored layer composited behind the subject, and the blur uses `ImageFilter.GaussianBlur` with masking.

### 5. Contextual awareness

If the conversation already contains an image or references a specific file (like a hero image on a website), tailor the prompt defaults to match that context. For example:

- Dark website background → default to `#0A0A0A`
- Hero image that needs to blend into text → suggest left-to-right fade starting at 55%
- Brand colors mentioned → use those as default glow color
- Portfolio / professional context → suggest subtle, ambient glow over neon

## Tips for the User

- These prompts work in ChatGPT (DALL-E), Midjourney, Adobe Firefly, and most AI image editors
- Fill in the `___` blanks with your values before pasting
- The parenthetical hints (e.g. `e.g. 55%`) are suggested defaults — adjust to taste
- For website hero images, gradient transparency is usually the most impactful single effect
- Glow colors that match your brand palette create visual cohesion
- When combining all three, the stack order matters: blur first (base layer), glow second (depth), fade last (blending)
