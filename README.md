# Shopify Liquid Theme Skills

A collection of Claude Agent Skills for Shopify Liquid theme development. Three skills organized by scope — Liquid language fundamentals, coding standards, and accessibility.

## Installation

```bash
claude skill install --plugin shopify-theme-skills benjaminsehl/liquid-skills
```

## Skills Overview

| Skill | Scope | SKILL.md | What Claude learns |
|-------|-------|----------|-------------------|
| [`skills/shopify-liquid-themes/`](#shopify-liquid-themes) | All Liquid themes | 318 lines | Schema JSON, LiquidDoc, filters, tags, objects, translations |
| [`skills/liquid-theme-standards/`](#liquid-theme-standards) | All Liquid themes | 420 lines | BEM in `{% stylesheet %}`, design tokens, Web Components, defensive CSS |
| [`skills/liquid-theme-a11y/`](#liquid-theme-a11y) | All Liquid themes | 448 lines | WCAG patterns for e-commerce components |

### How they relate

```
┌──────────────────────────────────────────────────┐
│  shopify-liquid-themes    (Liquid language)       │
│  liquid-theme-standards   (CSS/JS/HTML patterns)  │
│  liquid-theme-a11y        (Accessibility)         │
└──────────────────────────────────────────────────┘
```

All three skills work with any Shopify Liquid theme.

---

## shopify-liquid-themes

Liquid language fundamentals: schema format, 33 setting types, 152 filters, 30 tags, 137 objects, LiquidDoc, and translation patterns.

```
skills/shopify-liquid-themes/
├── SKILL.md
└── references/
    ├── filters-language.md     # 77 filters: array, string, math, date, default, format (auto-generated)
    ├── filters-html-media.md   # 45 filters: color, font, html, media, hosted file (auto-generated)
    ├── filters-commerce.md     # 30 filters: cart, collection, money, payment, etc. (auto-generated)
    ├── tags.md                 # 30 tags with syntax/examples (auto-generated)
    ├── objects-commerce.md     # 5 core commerce objects: product, variant, cart, order, line_item (auto-generated)
    ├── objects-content.md      # 10 content/theme objects: collection, customer, page, shop, etc. (auto-generated)
    ├── objects-tier2.md        # 69 objects with property lists (auto-generated)
    ├── objects-tier3.md        # 53 simple objects with access paths (auto-generated)
    ├── schema-and-settings.md  # Schema format, 33 setting types
    └── examples.md             # Full snippet/block/section examples
```

## liquid-theme-standards

CSS, JavaScript, and HTML coding standards for Shopify themes. Covers BEM naming inside `{% stylesheet %}` tags, design tokens with CSS custom properties, Web Component patterns, defensive CSS, logical properties for RTL, and progressive enhancement.

```
skills/liquid-theme-standards/
├── SKILL.md
└── references/
    ├── css-patterns.md         # Layout, animation, print styles
    └── javascript-patterns.md  # Web Components, events, data loading
```

## liquid-theme-a11y

WCAG 2.2 accessibility patterns for e-commerce components: product cards, carousels, cart drawers, forms, filters, price display, modals, navigation, and color swatches.

```
skills/liquid-theme-a11y/
├── SKILL.md
└── references/
    ├── component-patterns.md   # Color swatches, breadcrumbs, tables, sliders
    └── focus-and-keyboard.md   # Focus trapping, roving tabindex, announcements
```

