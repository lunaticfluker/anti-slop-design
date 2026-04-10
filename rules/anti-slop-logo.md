# Anti-Slop Logo & Typography Rules

Apply these when generating logos, wordmarks, or making typography decisions for brand identities.

## The AI tells in logo generation (never do these)

### Font selection
- **Don't default to Cormorant Garamond** — it's the #1 AI-generated font. Claude picks it 80% of the time if you list it as an example.
- **Don't default to serif** — modern default is sans-serif. Serif is a deliberate choice, not a fallback.
- **Don't use only serif examples** — if listing font options, span serif, sans, and geometric equally.
- **Don't describe font style when you already named the font** — "DM Sans" is enough. Adding "hairline thin strokes, sharp terminals" overrides the font name and produces a serif regardless.

### Prompt engineering
- **Don't reference luxury houses** — "Hermès, Bottega Veneta, Cartier" biases Ideogram/Midjourney toward one specific serif aesthetic. Say "contemporary typographic quality" instead.
- **Don't say "elegant high-contrast serif"** — this forces serif even when the font is "Inter."
- **Don't say "luxurious"** — say "clean, minimal, modern."
- **Do say the exact font name** — "Typeface: Space Grotesk" > "modern sans-serif typography."
- **Do use a negative prompt** — block: oversized text, decorative elements, gradients, multiple text lines, icons, symbols.

### Color & layout
- **Flat solid background** — not gradient, not textured, not patterned.
- **White text on brand color** — simplest, most versatile. Invert for light backgrounds.
- **One-third canvas width** — text too large is the #1 Ideogram artifact. Ask for small + compact.
- **Wide empty margins** — more space than you think.

## Good font recommendations by category

### Modern sans (clean, contemporary)
Inter, Space Grotesk, Outfit, Syne, Hanken Grotesk, General Sans

### Geometric sans (precise, tech-forward)  
DM Sans, Urbanist, Plus Jakarta Sans, Satoshi, Cabinet Grotesk

### Modern serif (refined, editorial)
DM Serif Display, Libre Baskerville, Fraunces, Instrument Serif

### Display (distinctive, brand-forward)
Unbounded, Syne, Space Mono (mono display), JetBrains Mono

**Rule:** Every brand should feel different. If your last 5 brands all got the same font, something is wrong.

## Post-processing pipeline (for programmatic logo generation)

When generating logos programmatically (Ideogram, Recraft), always post-process:

1. **Extract text as greyscale mask** — preserves anti-aliased edges
2. **Replace background with exact hex** — AI never gets the exact brand color right
3. **Enforce text size** — if text spans >60% or <40% of width, scale to ~50%
4. **Composite white text onto exact-color background** — crisp, consistent output
5. **Export both composited (WebP) and transparent (PNG)** — always provide both formats

This pipeline exists because AI models are unreliable at:
- Exact hex color reproduction
- Consistent text sizing
- Clean anti-aliased edges on colored backgrounds
