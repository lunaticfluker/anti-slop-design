# shadcn/ui Anti-Slop Guide

## Philosophy

shadcn/ui components are unstyled building blocks. The anti-slop approach: use the component logic, override the visual defaults to match your design system.

## Override pattern

Don't use shadcn defaults as-is — they're intentionally generic. Map to your design system variables:

```tsx
// shadcn default Button — generic
<Button variant="default">Click</Button>

// Anti-slop: override with your design system
<Button 
  className="bg-[var(--accent)] text-white font-mono text-[.6rem] tracking-[.15em] uppercase rounded-none hover:opacity-90"
>
  LABEL
</Button>
```

## Component overrides by design system

### Dark Editorial
```tsx
// Button
className="bg-[var(--accent)] text-white font-mono text-[.6rem] tracking-[.15em] uppercase px-6 py-3 rounded-none"

// Card
className="border border-[var(--line)] bg-[var(--bg-card)] rounded-none"

// Input
className="border border-[var(--line)] bg-[var(--bg)] rounded-none text-sm font-mono focus:border-[var(--accent)]"

// Dialog
className="border border-[var(--line)] bg-[var(--bg-raised)] rounded-none"
```

### Clean Professional
```tsx
// Button
className="bg-[var(--text)] text-white text-sm font-medium px-4 py-2 rounded-md"

// Card
className="border border-[var(--line)] rounded-lg"

// Input
className="border border-[var(--line)] rounded-md text-sm focus:border-[var(--accent)] focus:ring-1 focus:ring-[var(--accent)]"
```

## Components to use vs avoid

### Use freely
- `Button` — override styling
- `Dialog` / `Sheet` — good modal logic
- `Dropdown` / `Select` — accessible by default
- `Input` / `Textarea` — standard form controls
- `Tabs` — tab switching logic
- `Toast` — notification system
- `Tooltip` — hover info

### Use with caution
- `Card` — override the rounded + shadow defaults
- `Badge` — often over-decorated by default
- `Alert` — tends toward heavy styling

### Avoid (roll your own)
- `Accordion` — simple enough to build, shadcn's adds visual opinions
- `Avatar` — just use an img with rounded-full
- `Carousel` — heavy, usually better with a simpler scroll approach
- `Calendar` — extremely opinionated styling

## Key principle

shadcn gives you **behavior** (keyboard nav, focus management, a11y). You give it **appearance** (from your design system). If you're using shadcn's default colors and spacing, you're not designing — you're using a template.
