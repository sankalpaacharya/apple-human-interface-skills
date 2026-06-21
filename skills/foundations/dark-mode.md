# Dark Mode

> A systemwide dark color palette for low-light viewing that users expect every app and site to respect automatically.

**Use it for:** Any product that should honor the OS appearance preference, especially media- or reading-focused experiences that benefit from a recessive dark UI.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `prefers-color-scheme: dark` (or `color-scheme` + `light-dark()`), swap token values; `<meta name="theme-color">` |
| SwiftUI | Automatic via semantic `Color` + asset-catalog appearance variants; `@Environment(\.colorScheme)`, `.preferredColorScheme()` |
| Android (Compose) | `darkColorScheme()` vs `lightColorScheme()` selected by `isSystemInDarkTheme()` |
| React Native | `useColorScheme()` returning `'dark'`/`'light'`, theme context swap, `Appearance` API |
| Flutter | `ThemeData.dark()` + `darkTheme` on `MaterialApp`, `MediaQuery.platformBrightness` |

**Guidelines**
- Respect the system preference by default; don't force one mode without reason.
- If offering a manual toggle, default to "follow system" and persist the explicit choice.
- Theme via semantic tokens with light and dark values; avoid hard-coded colors.
- Dark palettes aren't inversions — use dim backgrounds with brighter (not pure-white) foreground text.
- Convey depth with layered surfaces: darker base recedes, lighter elevated surfaces (modals, cards) advance.
- Slightly dim large bright images; provide separate dark assets when an image only reads in one mode.
- Give icons that blend into the background a subtle outline in the weak-contrast mode; prefer adaptable vectors.

**Accessibility**
- Maintain contrast in both modes (≥4.5:1 text; aim 7:1 for small custom text).
- Test with increased-contrast and reduced-transparency preferences — dark-on-dark can fail when transparency drops.
- Web: set `color-scheme` so native controls/scrollbars render correctly and `theme-color` matches.

**Avoid**
- An app-only switch that ignores the OS setting (users may think it's broken).
- Hard-coded or pure-white text/backgrounds that glow in dark mode.
- Assuming a straight inversion produces a good dark theme.

**Full reference:** [Apple HIG](../../references/foundations/dark-mode.md)
