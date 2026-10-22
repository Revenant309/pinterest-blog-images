---
name: pinterest-blog-images
description: "Generates Pinterest-optimized images from a blog post URL or content using Grok Imagine. Use when the user wants Pinterest pins, visuals, or images based on a blog article or web post."
type: workflow
lifecycle: active
---

# Pinterest Blog Images

Creates a set of vertical Pinterest-ready images from a blog post (URL or pasted text) using Grok Imagine. Outputs images plus ready-to-use captions.

## When to use
Trigger when the user asks to create Pinterest pins, images, or visuals from a blog post, article URL, or web content.

## Core Workflow

1. **Get the source**
   - If the user provides a URL, use `browse_page` to extract the full article content, title, key points, tips, and any notable quotes.
   - If the user pastes text, use that directly.
   - Identify the main topic, audience, and 4–6 strongest visual ideas (hooks, tips, steps, quotes, problems/solutions).

2. **Plan the pin set**
   - Aim for 3–6 images covering different angles (see `references/pinterest-guidelines.md`).
   - Typical mix: 1 cover/hero, 1–2 tip or list pins, 1 quote (if available), 1 process or lifestyle visual.
   - Note short text overlays that would work on the image.

3. **Generate images**
   - For each idea, craft a detailed prompt that includes:
     - Visual description
     - "Pinterest pin style, vertical 2:3, high quality, vibrant, clean composition"
     - Optional short bold text overlay
     - Style variation (photo, illustration, minimalist, etc.)
   - Generate using the `render_generated_image` component with `orientation="portrait"`.
   - Generate them one after another in the response so they appear for the user.

4. **Deliver the package**
   - Show each generated image.
   - Under each image provide:
     - Suggested Pinterest title
     - Description (with keywords)
     - 5–8 hashtags
     - Optional CTA
   - End with a short summary of the pin strategy.

## Quality Rules
- Prefer portrait orientation always.
- Keep text overlays short and high-contrast when included in the prompt.
- Do not invent facts; base every visual idea on content from the source post.
- Vary the visual style across the set so the pins do not look identical.

## References
- Full guidelines, image types, and caption structure: `references/pinterest-guidelines.md`

## Common Issues
| Issue | Fix |
|-------|-----|
| Images look too similar | Explicitly request different styles (photo vs illustration vs flat design) in each prompt |
| Text is hard to read | Specify "bold, high-contrast text overlay, large readable font" in the prompt |
| Content not visual enough | Focus on the most concrete tips, steps, or emotional hooks instead of abstract ideas |
| URL fails to load | Ask the user to paste the main text of the post |
