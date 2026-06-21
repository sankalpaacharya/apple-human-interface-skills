# Color

> Use color deliberately to communicate status, express brand, convey hierarchy, and provide continuity — not as decoration.

**Use it for:** Establishing a brand accent and neutral scale, signaling status/feedback, and building a semantic token system that adapts to light, dark, and high-contrast.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | CSS custom properties / tokens (`--color-text`, `--color-accent`) with light/dark variants; `oklch()`/`display-p3` for wide gamut |
| SwiftUI | Semantic `Color` (`.primary`, `.secondary`), named asset-catalog colors with appearance variants, `.tint()` |
| Android (Compose) | `ColorScheme` roles (`primary`, `surface`, `onSurface`) in `MaterialTheme`, dynamic color |
| React Native | Token object + theme context, `useColorScheme()` to switch, platform `PlatformColor` |
| Flutter | `ColorScheme` (`primary`, `surface`, `onSurface`), `ThemeData`, `Theme.of(context)` |

**Guidelines**
- One meaning per color; don't reuse the interactive accent on non-interactive text.
- Define semantic tokens by purpose (text, secondary, separator, link, background levels), not raw appearance.
- Supply light, dark, and higher-contrast variants for every custom color; don't hard-code one value.
- Establish background hierarchy with primary/secondary/tertiary surface tokens for depth and grouping.
- Apply the accent sparingly — reserve it for primary actions or key status (one prominent action per toolbar).
- Over busy/media backgrounds, prefer monochromatic controls for legibility.
- Be mindful of cultural color meaning when color carries meaning.

**Accessibility**
- Never rely on color alone — pair with text, icons, or shape so colorblind users get the same info.
- Meet contrast: 4.5:1 normal text, 3:1 large text/UI components.
- Web: `prefers-color-scheme` and `prefers-contrast: more`. iOS: semantic colors + Increase Contrast. Android: dynamic/high-contrast themes.
- Validate accent-on-background and text-on-translucency in every mode.

**Avoid**
- Hard-coded values inline instead of tokens; redefining a token's meaning.
- Color as the sole signal for state, errors, or interactivity.
- Over-tinting many controls at once, killing emphasis.
- Low-contrast text on tinted/translucent surfaces.

**Full reference:** [Apple HIG](../../references/foundations/color.md)
