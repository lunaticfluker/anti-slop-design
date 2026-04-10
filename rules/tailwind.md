# Tailwind Anti-Slop Patterns

## CSS variables over hardcoded values

Always use CSS custom properties for the design system. This enables theming and consistency.

```html
<!-- Bad: hardcoded values scattered everywhere -->
<div class="bg-[#0A0A0A] text-[#E8E8E8] border-[#1E1E1E]">

<!-- Good: CSS variables from the design system -->
<div class="bg-[var(--bg)] text-[var(--text)] border-[var(--line)]">
```

## The AI-generated Tailwind tells

### Spacing
```html
<!-- AI slop: uniform padding -->
<section class="p-8">

<!-- Anti-slop: intentional asymmetric padding -->
<section class="px-6 md:px-[clamp(1.5rem,5vw,6rem)] py-10 md:py-16">
```

### Typography
```html
<!-- AI slop: basic text sizes -->
<h1 class="text-4xl font-bold">Title</h1>
<p class="text-gray-600">Body</p>

<!-- Anti-slop: design system typography -->
<div class="font-mono text-[.62rem] tracking-[.28em] uppercase text-[var(--accent)]">EYEBROW</div>
<h1 class="text-[clamp(1.8rem,3.5vw,3rem)] font-light uppercase tracking-[.05em]">Title</h1>
<p class="text-[.875rem] font-light leading-[1.7] text-[var(--dim)]">Body</p>
```

### Buttons
```html
<!-- AI slop: gradient + rounded-full + shadow -->
<button class="bg-gradient-to-r from-blue-500 to-purple-600 rounded-full shadow-lg px-6 py-3 text-white font-bold">
  Click me
</button>

<!-- Anti-slop: solid + sharp/subtle radius + no shadow -->
<button class="bg-[var(--accent)] text-white font-mono text-[.6rem] tracking-[.15em] uppercase px-6 py-3 hover:opacity-90 transition-opacity">
  LABEL
</button>
```

### Cards
```html
<!-- AI slop: shadow + rounded-2xl + gradient border -->
<div class="rounded-2xl shadow-xl bg-white p-6 border border-transparent bg-gradient-to-br from-purple-50 to-blue-50">

<!-- Anti-slop: border + sharp corners + solid bg -->
<div class="border border-[var(--line)] bg-[var(--bg-card)] p-6">
```

### Layout
```html
<!-- AI slop: centered everything, no max-width -->
<main class="text-center p-4">
  <div class="max-w-4xl mx-auto">

<!-- Anti-slop: left-aligned body, proper max-width + padding -->
<main class="px-6 md:px-[clamp(1.5rem,5vw,6rem)]">
  <div class="max-w-[1400px] mx-auto">
```

## Responsive patterns

```html
<!-- Mobile-first, responsive padding and gaps -->
<div class="px-4 md:px-8 lg:px-16">
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 md:gap-6">
<h1 class="text-2xl md:text-4xl lg:text-5xl">

<!-- Use clamp() for fluid typography -->
<h1 class="text-[clamp(1.8rem,3.5vw,3rem)]">
```

## Hover states

```html
<!-- AI slop: dramatic hover -->
<div class="hover:scale-105 hover:shadow-2xl hover:bg-gradient-to-r transition-all duration-500">

<!-- Anti-slop: subtle hover -->
<div class="hover:border-[var(--accent)] transition-colors duration-200">
<!-- or -->
<button class="hover:opacity-90 transition-opacity">
```

## Animation

```html
<!-- AI slop: bouncy, attention-seeking -->
<div class="animate-bounce hover:animate-pulse">

<!-- Anti-slop: subtle, purposeful -->
<div class="transition-all duration-200 ease-out">
<!-- Only animate: opacity, transform, color, border-color -->
<!-- Never animate: width, height, padding, margin (causes layout shift) -->
```
