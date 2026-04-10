# Anti-Slop Logo & Typography Rules

Apply these when generating logos, wordmarks, or making typography decisions for brand identities.

## The AI tells in logo generation (never do these)

### Font selection
- **Don't default to Cormorant Garamond** — it's the #1 AI-generated font. Claude picks it 80% of the time if you list it as an example.
- **Don't default to serif** — modern default is sans-serif. Serif is a deliberate choice, not a fallback.
- **Don't use only serif examples** — if listing font options, span serif, sans, and geometric equally.

### Prompt engineering
- **Don't reference luxury houses** — "Hermès, Bottega Veneta, Cartier" biases Ideogram/Midjourney toward one specific serif aesthetic.
- **Don't say "luxurious"** — say "clean, minimal, modern."
- **Do use a negative prompt** — block: oversized text, decorative elements, gradients, multiple text lines, icons, symbols.
- **Don't say just the font name** — AI image generators can't render actual fonts. "Typeface: Space Grotesk" alone makes the AI guess what that name looks like. Describe the letterform characteristics instead.

### Typography strategy: archetype-driven (how it works now)

The logo prompt is driven by the same visual archetype system that drives product/lifestyle/store photography. This ensures the logo's typographic personality matches the rest of the brand's visual world.

**How the prompt is assembled:**
1. Archetype `typographyStyle` leads — describes letterform characteristics using typographic vocabulary (grotesque, didone, humanist, neo-grotesque, geometric). This is the primary instruction the AI follows.
2. `headingFont` is a soft hint — "In the character of Space Grotesk" not "Typeface: Space Grotesk". The AI uses this as a reference point, not a literal font to render.
3. Voice descriptors add brand personality — "bold, unapologetic, raw" tells the AI the emotional weight.
4. `visualDirection` grounds the overall aesthetic — same one-sentence direction used across all images.
5. Spacing/kerning language — "Generous letter-spacing, optically kerned" prevents the AI from cramming letters.

**Why this works better than exact font names:**
- AI generators don't have font files — they interpret font names as vague visual concepts
- Typographic vocabulary (tight apertures, hairline serifs, uniform stroke weight) gives the AI specific visual properties to render
- Product photos already look good because they describe *physical materials and lighting*, not font names — the logo prompt now follows the same principle
- Each archetype maps to an industry cluster, so a sneaker brand (urban-edge) automatically gets different type than a ceramics brand (heritage-craft)

**The 6 archetype typography personalities (49 style entries, 680+ keywords):**
| Archetype | Type personality | Industries |
|---|---|---|
| urban-edge | Condensed grotesque, tight apertures, industrial weight | fashion, footwear, auto, eyewear, music, nightlife, bar, skateboard, street art, martial arts, boxing, tattoo, barbershop |
| heritage-craft | Refined transitional serif, high-contrast strokes, classical | food, restaurant, bakery, furniture, stationery, homeware, leather, art, blacksmith, metalwork |
| opulent-classic | High-contrast didone, hairline serifs, dramatic thick-thin | spirits, brewery, distillery, jewelry, fragrance, aviation, yacht, hotel, fine dining, finance, cigar |
| clean-modern | Neo-grotesque, neutral proportions, even stroke | real estate, beauty, medical, dental, education, consulting, law firm, accounting, insurance, cleaning, logistics, events |
| natural-organic | Humanist sans-serif, soft terminals, open apertures | wellness, outdoor, spa, float therapy, hair salon, nail salon, children, wedding, florist, sustainable, farm |
| tech-forward | Geometric sans-serif, uniform stroke, precise curves | tech, SaaS, AI, fitness, gaming, coworking, podcast, newsletter, creator, e-commerce |

### Color & layout
- **Flat solid background** — not gradient, not textured, not patterned.
- **White text on brand color** — simplest, most versatile. Invert for light backgrounds.
- **One-third canvas width** — text too large is the #1 Ideogram artifact. Ask for small + compact.
- **Wide empty margins** — more space than you think.

## Font pools — per archetype (59 verified Google Fonts)

Fonts are organized by archetype in the cosmic system prompt's TYPOGRAPHY section. Claude picks from the matching pool during brand synthesis. Each pool has 9-10 options with sub-style groups.

| Archetype | Sub-styles | Example fonts |
|---|---|---|
| urban-edge | Condensed, Industrial, Structural | Oswald, Barlow Condensed, Bebas Neue, Anton, Teko |
| heritage-craft | Editorial serif, Oldstyle, Characterful | DM Serif Display, Instrument Serif, EB Garamond, Fraunces |
| opulent-classic | Didone, High-contrast, Luxury | Bodoni Moda, Libre Bodoni, GFS Didot, Playfair Display |
| clean-modern | Neo-grotesque, Professional, Refined | Inter, Hanken Grotesk, Work Sans, Outfit, Schibsted Grotesk |
| natural-organic | Humanist, Rounded, Warm geometric | Cabin, Nunito Sans, Quicksand, Figtree, Maven Pro |
| tech-forward | Geometric, Engineered, Monospace | Sora, Urbanist, Jost, Space Grotesk, Space Mono |

Full list: see `TYPOGRAPHY — ARCHETYPE FONT MATCHING` section in `apps/worker/src/lib/prompts/cosmic-system.ts`.

**Rule:** Every brand should feel different. If your last 5 brands all got the same font, something is wrong.

## Logo model pipeline (swappable)

Models are tried in priority order via `LOGO_MODELS` array in `canvas-logo.ts`. Current order: FLUX 2 Pro (primary) → Ideogram v3 (fallback) → Recraft V4 SVG (last resort). To test a different model, edit the array — no other changes needed.

## Post-processing pipeline (for programmatic logo generation)

When generating logos programmatically (FLUX, Ideogram, Recraft), always post-process:

1. **Extract text as greyscale mask** — preserves anti-aliased edges
2. **Replace background with exact hex** — AI never gets the exact brand color right
3. **Enforce text size** — if text spans >60% or <40% of width, scale to ~50%
4. **Composite white text onto exact-color background** — crisp, consistent output
5. **Export both composited (WebP) and transparent (PNG)** — always provide both formats

This pipeline exists because AI models are unreliable at:
- Exact hex color reproduction
- Consistent text sizing
- Clean anti-aliased edges on colored backgrounds
