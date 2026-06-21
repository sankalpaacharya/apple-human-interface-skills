# Apple-style design tokens

Concrete numbers to turn "be consistent" into real values. These mirror Apple's iOS system styles. Treat them as sensible defaults, not gospel: Apple's exact values shift between releases, so verify against the live HIG or the SF Symbols / Apple Design Resources files if you need pixel accuracy.

Everything here is framework-neutral. Copy-paste blocks for CSS variables, Tailwind, and a `tokens.json` are at the bottom.

## Type scale (iOS text styles)

Sizes in points (treat as px on the web). Apple's hierarchy comes from a tight ramp plus weight, not from many sizes.

| Style | Size | Weight | Line height |
| --- | --- | --- | --- |
| Large Title | 34 | Regular / Bold | 41 |
| Title 1 | 28 | Regular | 34 |
| Title 2 | 22 | Regular | 28 |
| Title 3 | 20 | Regular | 25 |
| Headline | 17 | Semibold | 22 |
| Body | 17 | Regular | 22 |
| Callout | 16 | Regular | 21 |
| Subheadline | 15 | Regular | 20 |
| Footnote | 13 | Regular | 18 |
| Caption 1 | 12 | Regular | 16 |
| Caption 2 | 11 | Regular | 13 |

Rules: body text is 17, not 14-16. Use weight (Semibold/Bold) and color, not just size, to build hierarchy. Tighten letter-spacing slightly on large titles.

## Spacing (8pt grid)

Use multiples of 8, with 4 as a half-step. Be generous: Apple layouts breathe.

`2, 4, 8, 12, 16, 20, 24, 32, 40, 48, 64`

- Screen / container side margins: 16-20
- Gap between related items: 8-12
- Gap between sections: 24-32
- Touch target minimum: 44x44

## Corner radius

Apple uses large, soft, continuous corners (squircles). On the web, plain `border-radius` is close enough; for true squircles use a corner-smoothing lib.

| Token | Value | Use |
| --- | --- | --- |
| sm | 8 | small controls, tags |
| md | 12 | buttons, inputs |
| lg | 16 | cards, sheets |
| xl | 22 | large cards, modals |
| pill | 9999 | pills, segmented controls, avatars |

## Elevation / shadow

Subtle and soft. Avoid hard, dark drop shadows.

| Token | Value |
| --- | --- |
| sm | `0 1px 2px rgba(0,0,0,0.04), 0 1px 3px rgba(0,0,0,0.06)` |
| md | `0 4px 12px rgba(0,0,0,0.08)` |
| lg | `0 12px 32px rgba(0,0,0,0.12)` |

Material (translucency): `background: rgba(255,255,255,0.72); backdrop-filter: blur(20px) saturate(180%);` (use a dark base in dark mode). Always set a solid fallback for browsers without `backdrop-filter`.

## Motion

Apple motion is spring-based and quick, never linear. Respect reduced-motion.

- Standard ease: `cubic-bezier(0.4, 0.0, 0.2, 1)`, 200-300ms
- Spring feel (where supported): `linear()` spring or a physics lib with response ~0.4-0.5, damping ~0.8
- Entrances: fade + small move/scale (8-12px, 0.96-1.0), not slides across the screen
- Always gate with `@media (prefers-reduced-motion: reduce)` -> near-instant, no transform

## Color: iOS system palette

Reference hex values, light and dark. The accent colors are the recognizable ones; the grays and semantic labels are what make layouts feel calm and "system."

### Accent

| Name | Light | Dark |
| --- | --- | --- |
| Blue | #007AFF | #0A84FF |
| Green | #34C759 | #30D158 |
| Indigo | #5856D6 | #5E5CE6 |
| Orange | #FF9500 | #FF9F0A |
| Pink | #FF2D55 | #FF375F |
| Purple | #AF52DE | #BF5AF2 |
| Red | #FF3B30 | #FF453A |
| Teal | #30B0C7 | #40CBE0 |
| Yellow | #FFCC00 | #FFD60A |
| Mint | #00C7BE | #63E6E2 |
| Cyan | #32ADE6 | #64D2FF |

Pick **one** accent and use it sparingly (primary action, selection, links). Blue is the safe default.

### Gray ramp

| Name | Light | Dark |
| --- | --- | --- |
| Gray | #8E8E93 | #8E8E93 |
| Gray 2 | #AEAEB2 | #636366 |
| Gray 3 | #C7C7CC | #48484A |
| Gray 4 | #D1D1D6 | #3A3A3C |
| Gray 5 | #E5E5EA | #2C2C2E |
| Gray 6 | #F2F2F7 | #1C1C1E |

### Backgrounds

| Name | Light | Dark |
| --- | --- | --- |
| Background | #FFFFFF | #000000 |
| Secondary | #F2F2F7 | #1C1C1E |
| Tertiary | #FFFFFF | #2C2C2E |
| Grouped | #F2F2F7 | #000000 |

### Text / separators (use opacity over the base)

| Name | Light | Dark |
| --- | --- | --- |
| Label | #000000 | #FFFFFF |
| Secondary label | rgba(60,60,67,0.60) | rgba(235,235,245,0.60) |
| Tertiary label | rgba(60,60,67,0.30) | rgba(235,235,245,0.30) |
| Separator | rgba(60,60,67,0.29) | rgba(84,84,88,0.60) |

---

## Copy-paste: CSS variables

```css
:root {
  /* type */
  --font-sans: -apple-system, BlinkMacSystemFont, "SF Pro Text", "Inter", "Segoe UI", Roboto, sans-serif;
  --font-mono: ui-monospace, "SF Mono", "JetBrains Mono", Menlo, monospace;
  --text-large-title: 34px;  --text-title1: 28px; --text-title2: 22px; --text-title3: 20px;
  --text-headline: 17px; --text-body: 17px; --text-callout: 16px;
  --text-subhead: 15px; --text-footnote: 13px; --text-caption: 12px;

  /* spacing (8pt) */
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px;
  --space-5: 20px; --space-6: 24px; --space-8: 32px; --space-10: 40px; --space-12: 48px;

  /* radius */
  --radius-sm: 8px; --radius-md: 12px; --radius-lg: 16px; --radius-xl: 22px; --radius-pill: 9999px;

  /* shadow */
  --shadow-sm: 0 1px 2px rgba(0,0,0,.04), 0 1px 3px rgba(0,0,0,.06);
  --shadow-md: 0 4px 12px rgba(0,0,0,.08);
  --shadow-lg: 0 12px 32px rgba(0,0,0,.12);

  /* color (light) */
  --accent: #007AFF;
  --bg: #FFFFFF; --bg-secondary: #F2F2F7; --bg-tertiary: #FFFFFF;
  --label: #000000; --label-secondary: rgba(60,60,67,.6); --label-tertiary: rgba(60,60,67,.3);
  --separator: rgba(60,60,67,.29);
  --gray: #8E8E93; --gray5: #E5E5EA; --gray6: #F2F2F7;

  /* motion */
  --ease: cubic-bezier(.4,0,.2,1);
  --duration: 240ms;
}

@media (prefers-color-scheme: dark) {
  :root {
    --accent: #0A84FF;
    --bg: #000000; --bg-secondary: #1C1C1E; --bg-tertiary: #2C2C2E;
    --label: #FFFFFF; --label-secondary: rgba(235,235,245,.6); --label-tertiary: rgba(235,235,245,.3);
    --separator: rgba(84,84,88,.6);
    --gray5: #2C2C2E; --gray6: #1C1C1E;
  }
}

@media (prefers-reduced-motion: reduce) {
  * { transition-duration: 0.01ms !important; animation-duration: 0.01ms !important; }
}
```

## Copy-paste: Tailwind (theme extend)

```js
// tailwind.config.js  (Tailwind v3). For v4, put the same values in @theme in your CSS.
export default {
  theme: {
    extend: {
      fontFamily: {
        sans: ['-apple-system','BlinkMacSystemFont','SF Pro Text','Inter','Segoe UI','sans-serif'],
        mono: ['ui-monospace','SF Mono','JetBrains Mono','Menlo','monospace'],
      },
      fontSize: {
        'large-title': ['34px','41px'], title1: ['28px','34px'], title2: ['22px','28px'],
        title3: ['20px','25px'], headline: ['17px','22px'], body: ['17px','22px'],
        callout: ['16px','21px'], subhead: ['15px','20px'], footnote: ['13px','18px'], caption: ['12px','16px'],
      },
      spacing: { 1:'4px',2:'8px',3:'12px',4:'16px',5:'20px',6:'24px',8:'32px',10:'40px',12:'48px' },
      borderRadius: { sm:'8px', md:'12px', lg:'16px', xl:'22px', full:'9999px' },
      boxShadow: {
        sm:'0 1px 2px rgba(0,0,0,.04), 0 1px 3px rgba(0,0,0,.06)',
        md:'0 4px 12px rgba(0,0,0,.08)', lg:'0 12px 32px rgba(0,0,0,.12)',
      },
      colors: {
        accent: { DEFAULT:'#007AFF', dark:'#0A84FF' },
        label: { DEFAULT:'#000', secondary:'rgba(60,60,67,.6)', tertiary:'rgba(60,60,67,.3)' },
        surface: { DEFAULT:'#fff', secondary:'#F2F2F7', tertiary:'#fff' },
      },
    },
  },
}
```

## Copy-paste: tokens.json

```json
{
  "font": { "sans": "-apple-system, BlinkMacSystemFont, 'SF Pro Text', Inter, 'Segoe UI', sans-serif", "mono": "ui-monospace, 'SF Mono', 'JetBrains Mono', Menlo, monospace" },
  "type": { "largeTitle": [34,41], "title1": [28,34], "title2": [22,28], "title3": [20,25], "headline": [17,22], "body": [17,22], "callout": [16,21], "subhead": [15,20], "footnote": [13,18], "caption": [12,16] },
  "space": [4,8,12,16,20,24,32,40,48,64],
  "radius": { "sm": 8, "md": 12, "lg": 16, "xl": 22, "pill": 9999 },
  "shadow": { "sm": "0 1px 2px rgba(0,0,0,.04), 0 1px 3px rgba(0,0,0,.06)", "md": "0 4px 12px rgba(0,0,0,.08)", "lg": "0 12px 32px rgba(0,0,0,.12)" },
  "color": {
    "light": { "accent": "#007AFF", "bg": "#FFFFFF", "bgSecondary": "#F2F2F7", "label": "#000000", "labelSecondary": "rgba(60,60,67,.6)", "separator": "rgba(60,60,67,.29)" },
    "dark":  { "accent": "#0A84FF", "bg": "#000000", "bgSecondary": "#1C1C1E", "label": "#FFFFFF", "labelSecondary": "rgba(235,235,245,.6)", "separator": "rgba(84,84,88,.6)" }
  },
  "motion": { "ease": "cubic-bezier(.4,0,.2,1)", "duration": 240 }
}
```
