# Clean Professional Design System

For B2B SaaS, dashboards, dev tools, documentation. Think Linear, Vercel, Notion, Resend.

## Color Palette

```css
:root {
  --bg:          #FFFFFF;
  --bg-raised:   #FAFAFA;
  --bg-card:     #F5F5F5;
  --line:        #E5E5E5;
  --muted:       #A3A3A3;
  --dim:         #737373;
  --text:        #171717;
  --text-bright: #000000;
  --accent:      /* one accent — blue, violet, or green */;
  --accent-dim:  /* accent at 15% opacity for subtle backgrounds */;
}
```

**Rule:** Pure neutrals (gray-50 through gray-950). One functional accent. No warm tones unless the brand requires it.

## Dark mode (if needed)

```css
.dark {
  --bg:          #09090B;
  --bg-raised:   #18181B;
  --bg-card:     #27272A;
  --line:        #3F3F46;
  --muted:       #71717A;
  --dim:         #A1A1AA;
  --text:        #FAFAFA;
  --text-bright: #FFFFFF;
}
```

## Typography

```css
--font-heading: 'Inter', system-ui, sans-serif;
--font-body:    'Inter', system-ui, sans-serif;
--font-mono:    'JetBrains Mono', 'Fira Code', monospace;

--text-xs:   0.75rem;   /* 12px */
--text-sm:   0.875rem;  /* 14px — default body */
--text-base: 1rem;      /* 16px */
--text-lg:   1.125rem;  /* 18px */
--text-xl:   1.25rem;   /* 20px */
--text-2xl:  1.5rem;    /* 24px */
--text-hero: clamp(2rem, 3.5vw, 3rem);
```

**Body:** 14px, weight 400, line-height 1.6. Compact and information-dense.
**Headings:** weight 600, sentence case, tight tracking.
**Code:** mono, 13px, bg-card background, 2px border-radius.

## Spacing

```css
--space-page-x:    clamp(1rem, 3vw, 3rem);
--space-section-y: clamp(3rem, 6vw, 6rem);
--space-gap:       1rem;
--max-width:       1280px;
```

**Rule:** Tighter than editorial systems. Information density matters. But still generous enough to breathe.

## Components

### Button (primary)
```html
<button class="bg-[var(--text)] text-white text-sm font-medium px-4 py-2 rounded-md hover:opacity-90 transition-opacity">
  Label
</button>
```
Border-radius: 6px. Compact padding. No uppercase.

### Button (secondary)
```html
<button class="border border-[var(--line)] text-[var(--text)] text-sm font-medium px-4 py-2 rounded-md hover:bg-[var(--bg-card)] transition-colors">
  Label
</button>
```

### Card
```html
<div class="border border-[var(--line)] rounded-lg p-5">
  <h3 class="text-base font-semibold">Title</h3>
  <p class="text-sm text-[var(--dim)] leading-relaxed mt-2">Description.</p>
</div>
```
Border + subtle radius (8px). No shadow.

### Input
```html
<input class="w-full border border-[var(--line)] rounded-md px-3 py-2 text-sm bg-[var(--bg)] focus:border-[var(--accent)] focus:ring-1 focus:ring-[var(--accent)] outline-none transition-colors" />
```

## Layout rules
- Max-width 1280px
- Consistent 8px grid (all spacing multiples of 8)
- Sidebar + main content pattern for dashboards
- Tables and lists are first-class citizens
- Tight vertical rhythm — sections closer together than editorial systems

## Don'ts for this system
- No decorative elements (no illustrations, no patterns)
- No large hero images (use product screenshots or nothing)
- No rounded-full buttons (6-8px radius max)
- No dramatic hover animations (subtle opacity or background change only)
- No warm tones in the neutral palette (pure gray, not warm gray)
