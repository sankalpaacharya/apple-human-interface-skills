# Typography

> Typographic choices establish legibility, hierarchy, and brand through deliberate use of size, weight, and a limited set of typefaces.

**Use it for:** Building a reusable type scale, conveying hierarchy without extra typefaces, and ensuring text scales with user/OS font-size settings.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Type scale in `rem`/`em` tokens + `clamp()`; `system-ui`/variable fonts; semantic classes (`.title`, `.body`) |
| SwiftUI | `Font` text styles (`.largeTitle`…`.caption`), Dynamic Type, `@ScaledMetric`, custom `Font` with relative scaling |
| Android (Compose) | `MaterialTheme.typography` styles, `sp` units (auto font scaling), `FontFamily` |
| React Native | `StyleSheet` with `fontSize`/`fontWeight`, `allowFontScaling`, theme type tokens, `PixelRatio.getFontScale()` |
| Flutter | `TextTheme` styles (`titleLarge`, `bodyMedium`), `MediaQuery.textScaler`, `TextStyle` |

**Guidelines**
- Define a semantic type scale (large title → title → headline → body → caption) and reuse it.
- Minimize the number of typefaces; mixing many obscures hierarchy.
- Convey hierarchy with weight, size, and color; keep relative hierarchy intact when text scales.
- Body text ~16–17pt baseline; keep a sensible minimum (~11–12pt) for small labels.
- Prefer Regular/Medium/Semibold/Bold; avoid Thin/Light weights at small sizes.
- Use system font stacks for performance and native feel; if custom, prefer variable fonts that scale and bold correctly.
- Adjust line height to context — looser for long passages, tighter for dense rows.
- Constrain measure (~45–75 chars); reduce columns as text grows.
- Size paired icons relatively so they grow alongside text.

**Accessibility**
- Use relative/scalable units and Dynamic Type / font scaling — never fixed `px` for body copy.
- Web: don't disable user zoom; test at 200% text size.
- Prioritize key content when scaling — let body grow even if chrome stays put.
- Keep strong contrast; let labels wrap instead of truncating at large sizes.

**Avoid**
- Many competing typefaces or light/thin weights for important text.
- Pixel-locked font sizes that ignore user preferences.
- Truncating meaningful text instead of wrapping when font size increases.

**Full reference:** [Apple HIG](../../references/foundations/typography.md)
