# Anti-Slop UI Rules

Apply these to every UI you build. These are the design equivalent of "nothing symmetrical, nothing perfect."

## The AI tells (never do these)

### Layout
- **No centered paragraph text.** Left-align body copy. Center only headings, CTAs, and hero one-liners.
- **No symmetrical layouts by default.** Use asymmetric grids (60/40, 70/30). Break the grid once per page.
- **No full-width everything.** Set a max-width (1200-1400px). Let the content breathe.
- **No equal spacing everywhere.** Sections need different vertical rhythm — hero gets more, content less.

### Color
- **No gradient backgrounds** unless the design system explicitly calls for it.
- **No blue-to-purple gradient CTAs.** This is the #1 AI design tell. Use solid colors.
- **No neon accents on dark backgrounds** unless you're deliberately going cyberpunk.
- **No more than one accent color.** Pick one. Use it sparingly.
- **No colored text on colored backgrounds.** White or near-black on everything.

### Typography
- **No decorative fonts for body text.** Body = clean sans or readable serif. Period.
- **No more than 2 font families** (heading + body). 3 max if you need a monospace.
- **No tiny font sizes for important text.** Minimum 16px for body on web.
- **No uniform font weight.** Use at least 3 weights: light (headings), regular (body), semibold (emphasis).
- **No emoji in professional headings.** Icons are acceptable; emoji are not.

### Components
- **No rounded-3xl on everything.** Either sharp corners (editorial) or subtle radius (4-8px). Pick one.
- **No drop shadows on every card.** Use borders or background color difference instead. One shadow per page max.
- **No hover effects on everything.** Only interactive elements get hover states.
- **No glassmorphism** unless it's the core aesthetic. Backdrop-blur is expensive and looks AI-generated.
- **No floating orbs, particles, or aurora backgrounds.** These are AI design wallpaper.

### Images & media
- **No stock photo heroes.** Use solid color, typography, illustration, or nothing.
- **No decorative illustrations that don't communicate.** Every visual must earn its space.
- **No placeholder "abstract" hero images.** If you don't have real imagery, use typography.

## The anti-slop defaults

When in doubt, apply these:

```
Background:     solid color (not gradient)
Border radius:  0px (editorial) or 6px (product)
Shadows:        none (use borders instead)
Spacing:        more than you think (1.5x your first instinct)
Font weight:    lighter than you think (300 for display, 400 for body)
Color palette:  2 colors (bg + accent) + grays
Hover state:    subtle (opacity, underline, or border) not dramatic
Animation:      opacity + transform only, 200ms, ease-out
Hero:           typography-driven, not image-driven
CTA:            solid fill, not gradient, not outlined
Cards:          border, not shadow
```

## Spacing philosophy

The #1 differentiator between AI-generated and human-designed UI is spacing. AI under-spaces everything.

```
Section padding:     80-120px vertical (not 40px)
Content max-width:   1200px (not full-width)
Heading margin:      48-64px above, 16-24px below (not 24px both)
Paragraph spacing:   1.6-1.8 line-height (not 1.5)
Component gap:       24-32px between cards (not 16px)
Page padding:        24-48px horizontal (responsive)
```

## Typography hierarchy

Size alone doesn't create hierarchy. Use the full stack:

1. **Size** — 3-4 distinct sizes, with clear jumps (not 14/16/18/20 — use 14/18/28/48)
2. **Weight** — light (300) for large display, regular (400) for body, semibold (600) for labels
3. **Case** — uppercase + letter-spacing for labels/eyebrows, sentence case for everything else
4. **Color** — primary for headings, muted for secondary, very-muted for tertiary
5. **Font family** — mono for labels/metadata, sans for everything else

The AI tell: using only size to differentiate hierarchy. Human designers use all 5.
