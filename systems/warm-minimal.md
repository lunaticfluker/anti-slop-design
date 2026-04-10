# Warm Minimal Design System

For food, wellness, lifestyle, hospitality, editorial brands. Think Kinfolk, Cereal Magazine, Aesop, Wildsmith.

## Color Palette

```css
:root {
  --bg:          #FAF8F4;
  --bg-raised:   #FFFFFF;
  --bg-card:     #F2EFE9;
  --line:        #E5E0D8;
  --muted:       #A09888;
  --dim:         #7A7164;
  --text:        #2C2824;
  --text-bright: #1A1714;
  --accent:      /* your brand color — one warm tone */;
  --accent-dim:  /* accent at 30% opacity */;
}
```

**Rule:** Warm neutrals only. No pure white (#FFF), no pure black (#000). Everything has warmth.

## Typography

```css
--font-heading: 'DM Serif Display', 'Libre Baskerville', Georgia, serif;
--font-body:    'Inter', 'DM Sans', system-ui, sans-serif;
--font-mono:    'IBM Plex Mono', monospace;

--text-xs:   0.6875rem; /* 11px */
--text-sm:   0.8125rem; /* 13px */
--text-base: 1rem;      /* 16px — larger body for readability */
--text-lg:   1.125rem;  /* 18px */
--text-xl:   1.5rem;    /* 24px */
--text-2xl:  2rem;      /* 32px */
--text-hero: clamp(2.5rem, 5vw, 4rem);
```

**Body:** 16px, weight 400, line-height 1.8 (generous). Serif heading + sans body.
**Headings:** weight 400 (regular serif is already expressive), sentence case, tracking normal.
**Labels:** mono, uppercase, 11px, tracking 0.2em, muted color.

## Spacing

```css
--space-page-x:    clamp(2rem, 6vw, 8rem);
--space-section-y: clamp(5rem, 10vw, 10rem);  /* very generous */
--space-gap:       2rem;
--max-width:       1200px;  /* narrower than dark editorial */
```

**Rule:** More whitespace than you think. This system breathes. When in doubt, add 50% more vertical space.

## Components

### Button (primary)
```html
<button class="bg-[var(--text)] text-[var(--bg)] font-sans text-sm tracking-wide px-8 py-3.5 hover:opacity-80 transition-opacity">
  Label
</button>
```
No uppercase. Sentence case. Subtle. Border-radius: 0 or 2px max.

### Button (secondary)
```html
<button class="border border-[var(--text)] text-[var(--text)] font-sans text-sm tracking-wide px-8 py-3.5 hover:bg-[var(--text)] hover:text-[var(--bg)] transition-colors">
  Label
</button>
```

### Card
```html
<div class="bg-[var(--bg-card)] p-8">
  <span class="font-mono text-[.6875rem] tracking-[.2em] uppercase text-[var(--muted)]">Label</span>
  <h3 class="font-serif text-2xl mt-3">Title here</h3>
  <p class="text-base text-[var(--dim)] leading-[1.8] mt-4">Description with generous line height.</p>
</div>
```
No border. Background color difference creates separation. No shadow.

## Layout rules
- Max-width 1200px (narrower = more editorial)
- Generous horizontal padding (up to 128px on wide screens)
- Asymmetric grids: 60/40 or 70/30 splits
- Large imagery with no borders (images bleed to card edge)
- Sections separated by space, not lines

## Don'ts for this system
- No pure white or pure black
- No sharp UI elements (buttons get 0-2px radius)
- No heavy font weights (max 500)
- No card borders (use background color difference)
- No neon or saturated accents (warm, muted tones only)
