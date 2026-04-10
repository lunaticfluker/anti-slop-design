---
name: anti-slop-design
description: "Opinionated anti-slop design for UI, photos, and logos. 4 complete design systems, anti-slop rules for every visual output Claude Code produces. Use when building UI, writing image prompts, generating logos, choosing colors/fonts, or designing layouts. Also use when the user says 'this looks AI-generated', 'make this modern', 'pick a design system', or 'anti-slop'."
---

# Anti-Slop Design

Opinionated design intelligence. Not 161 palettes — 4 complete systems. Not 50 styles — THE answer for your use case.

## How it works

**Detect the context, apply the right rules:**

| You're doing... | Load this |
|---|---|
| Writing CSS/JSX/HTML | [anti-slop-ui.md](rules/anti-slop-ui.md) + the appropriate [design system](systems/) |
| Writing a FLUX/Midjourney/DALL-E prompt | [anti-slop-photo.md](rules/anti-slop-photo.md) |
| Generating a logo/wordmark | [anti-slop-logo.md](rules/anti-slop-logo.md) |
| Using Tailwind CSS | [tailwind.md](rules/tailwind.md) + the appropriate [design system](systems/) |
| Using shadcn/ui | [shadcn.md](rules/shadcn.md) + the appropriate [design system](systems/) |
| Choosing colors or fonts | The appropriate [design system](systems/) |

## The 4 Design Systems

Each is a **complete decision stack** — palette, fonts, spacing, components, layout. Pick one and commit. Don't mix.

| System | File | Vibe | Best for |
|---|---|---|---|
| **Dark Editorial** | [dark-editorial.md](systems/dark-editorial.md) | Linear dark / Raycast / Arc | SaaS, creative tools, portfolios, developer products |
| **Warm Minimal** | [warm-minimal.md](systems/warm-minimal.md) | Kinfolk / Cereal / Aesop | Food, wellness, lifestyle, hospitality, editorial |
| **Clean Professional** | [clean-professional.md](systems/clean-professional.md) | Linear / Vercel / Notion | B2B SaaS, dashboards, dev tools, documentation |
| **Bold Commerce** | [bold-commerce.md](systems/bold-commerce.md) | Shopify / Stripe / Gumroad | E-commerce, pricing pages, marketplaces, checkout |

## Quick decision

- Dark background? → **Dark Editorial**
- Light, warm, lots of breathing room? → **Warm Minimal**
- Light, neutral, productivity-focused? → **Clean Professional**
- Needs to convert visitors to buyers? → **Bold Commerce**

## The anti-slop philosophy

AI-generated design has tells. This skill eliminates them:

1. **Opinionated > optional** — one answer, not fifty
2. **Spacing > decoration** — add whitespace, not gradients
3. **Typography hierarchy > color hierarchy** — size and weight before color
4. **Asymmetry > symmetry** — break the grid deliberately
5. **Restraint > expression** — fewer elements, each earning its place
