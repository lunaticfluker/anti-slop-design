# Bold Commerce Design System

For e-commerce, pricing pages, marketplaces, checkout flows. Think Shopify, Stripe, Gumroad, Lemonsqueezy.

## Color Palette

```css
:root {
  --bg:          #FFFFFF;
  --bg-raised:   #F9FAFB;
  --bg-card:     #F3F4F6;
  --bg-highlight:#FFF7ED;  /* warm highlight for featured items */
  --line:        #E5E7EB;
  --muted:       #9CA3AF;
  --dim:         #6B7280;
  --text:        #111827;
  --text-bright: #000000;
  --accent:      /* strong, high-contrast — action color */;
  --success:     #059669;
  --warning:     #D97706;
  --error:       #DC2626;
}
```

**Rule:** This system uses semantic colors (success, warning, error) because commerce needs clear status. Keep accent for CTAs only.

## Typography

```css
--font-heading: 'Inter', system-ui, sans-serif;
--font-body:    'Inter', system-ui, sans-serif;
--font-mono:    'JetBrains Mono', monospace;  /* for prices */

--text-xs:   0.75rem;   /* 12px */
--text-sm:   0.875rem;  /* 14px */
--text-base: 1rem;      /* 16px — body */
--text-lg:   1.25rem;   /* 20px */
--text-xl:   1.5rem;    /* 24px */
--text-2xl:  2rem;      /* 32px */
--text-price: clamp(2.5rem, 4vw, 4rem);  /* hero pricing */
```

**Prices:** Large, bold, mono. The price is the most important element on a commerce page.
**Body:** 16px, weight 400, line-height 1.6.
**CTAs:** 14-16px, weight 600, sentence case.

## Spacing

```css
--space-page-x:    clamp(1rem, 4vw, 4rem);
--space-section-y: clamp(3rem, 6vw, 6rem);
--space-gap:       1.5rem;
--max-width:       1200px;
```

## Components

### Button (primary CTA)
```html
<button class="bg-[var(--accent)] text-white text-base font-semibold px-8 py-3.5 rounded-lg hover:opacity-90 transition-opacity shadow-sm">
  Buy now — $97
</button>
```
Larger than other systems. Prominent. One shadow (sm) is acceptable for primary CTA only.

### Button (secondary)
```html
<button class="border-2 border-[var(--text)] text-[var(--text)] text-base font-semibold px-8 py-3.5 rounded-lg hover:bg-[var(--text)] hover:text-white transition-colors">
  Learn more
</button>
```

### Pricing card
```html
<div class="border border-[var(--line)] rounded-xl p-8 relative">
  <span class="font-mono text-xs tracking-wider uppercase text-[var(--muted)]">Pro</span>
  <div class="mt-4">
    <span class="text-[var(--text)] font-mono text-4xl font-bold">$97</span>
    <span class="text-[var(--dim)] text-sm ml-1">/one-time</span>
  </div>
  <ul class="mt-6 space-y-3 text-sm text-[var(--dim)]">
    <li class="flex items-center gap-2">
      <span class="text-[var(--success)]">&#10003;</span> Feature one
    </li>
  </ul>
  <button class="w-full mt-8 bg-[var(--accent)] text-white py-3 rounded-lg font-semibold">
    Get started
  </button>
</div>
```

### Trust badge
```html
<div class="flex items-center gap-2 text-[var(--muted)]">
  <span class="text-xs font-mono tracking-wider uppercase">Secure checkout</span>
</div>
```

## Layout rules
- Max-width 1200px
- Pricing grids: 2-3 columns, equal width, one highlighted
- Product grids: 3-4 columns, consistent card sizes
- Trust signals below CTAs (not above)
- Price always visible without scrolling
- Mobile: stack pricing cards vertically, sticky CTA at bottom

## Don'ts for this system
- No gradient CTAs (solid color, always)
- No tiny prices (price is the hero element)
- No decorative illustrations near checkout (distraction)
- No more than one CTA style per section
- No "most popular" badges with gradients (simple border or background highlight)
- No rounded-full buttons for primary actions (rounded-lg max)
