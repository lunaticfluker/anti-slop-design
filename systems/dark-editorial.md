# Dark Editorial Design System

For SaaS, creative tools, portfolios, developer products. Think Linear dark mode, Raycast, Arc, Warp.

## Color Palette

```css
:root {
  --bg:          #0A0A0A;
  --bg-raised:   #111111;
  --bg-card:     #161616;
  --line:        #1E1E1E;
  --muted:       #666666;
  --dim:         #999999;
  --text:        #E8E8E8;
  --text-bright: #FFFFFF;
  --accent:      /* your brand color — one only */;
  --accent-dim:  /* accent at 40% opacity */;
}
```

**Rule:** One accent color. Everything else is grayscale. The accent earns its impact by being rare.

## Typography

```css
--font-heading: 'Inter', system-ui, sans-serif;
--font-body:    'Inter', system-ui, sans-serif;
--font-mono:    'IBM Plex Mono', 'JetBrains Mono', monospace;

--text-xs:   0.625rem;  /* 10px — labels, metadata */
--text-sm:   0.75rem;   /* 12px — captions, eyebrows */
--text-base: 0.875rem;  /* 14px — body */
--text-lg:   0.95rem;   /* 15.2px — emphasis */
--text-xl:   1.25rem;   /* 20px — section headers */
--text-2xl:  1.75rem;   /* 28px — page titles */
--text-hero: clamp(2rem, 4vw, 3.5rem); /* hero headline */
```

**Eyebrow pattern:** mono, 10px, tracking 0.15em, uppercase, accent color.
**Body:** 14px, weight 400, line-height 1.7, text color (not bright white).
**Headings:** weight 300 (light), uppercase, tracking 0.05em.

## Spacing

```css
--space-page-x:    clamp(1.5rem, 5vw, 6rem);
--space-section-y: clamp(4rem, 8vw, 8rem);
--space-gap:       1.5rem;  /* between cards/items */
--max-width:       1400px;
```

## Components

### Button (primary)
```html
<button class="bg-[var(--accent)] text-white font-mono text-[.6rem] tracking-[.15em] uppercase px-6 py-3 hover:opacity-90 transition-opacity">
  LABEL
</button>
```
No border-radius. No shadow. No gradient.

### Button (secondary)
```html
<button class="border border-[var(--dim)] text-white font-mono text-[.6rem] tracking-[.15em] uppercase px-6 py-3 hover:border-[var(--accent)] transition-colors">
  LABEL
</button>
```

### Card
```html
<div class="border border-[var(--line)] bg-[var(--bg-card)] p-6">
  <div class="font-mono text-[.6rem] tracking-[.2em] uppercase text-[var(--accent)] mb-2">LABEL</div>
  <h3 class="text-xl font-light uppercase tracking-[.04em]">Title</h3>
  <p class="text-sm text-[var(--dim)] leading-[1.7] mt-3">Description</p>
</div>
```
No border-radius. No shadow. Border only.

### Divider
```html
<div class="h-px bg-[var(--line)]"></div>
```

## Layout rules
- Max-width 1400px, centered
- Horizontal padding responsive: 24px mobile, up to 96px desktop
- Sections separated by single 1px lines (var(--line)), not spacing alone
- Content breathes — 80-120px between major sections
- No full-bleed backgrounds — everything contained

## Don'ts for this system
- No rounded corners (sharp edges = editorial)
- No card shadows (borders only)
- No gradient CTAs
- No colored body text (gray scale only, accent for labels/links)
- No more than one accent color
