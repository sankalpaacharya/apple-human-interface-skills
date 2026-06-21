# Layout

> A consistent, adaptive layout grounds people in content and works across screen sizes and orientations.

**Use it for:** Designing screen structure, grouping content vs. controls, and adapting to viewport size, orientation, zoom, and device cutouts.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | CSS Grid/Flexbox, container/media queries, fluid units (`fr`, `minmax`, `clamp`), `env(safe-area-inset-*)` |
| SwiftUI | `Stack`s, `Grid`, `GeometryReader`, size classes (`@Environment(\.horizontalSizeClass)`), `.safeAreaInset`/`.ignoresSafeArea` |
| Android (Compose) | `Row`/`Column`/`Box`, `LazyColumn`, `WindowSizeClass`, `Modifier.windowInsetsPadding`/`safeDrawing` |
| React Native | Flexbox layout, `useWindowDimensions`, `Dimensions`, `react-native-safe-area-context` insets |
| Flutter | `Row`/`Column`/`Flex`, `LayoutBuilder`, `MediaQuery`, `SafeArea`, `Expanded`/`Flexible` |

**Guidelines**
- Group related items with whitespace, shapes, separators, or cards; keep content and controls distinct.
- Give essential info room; defer secondary content via progressive disclosure.
- Extend backgrounds/full-bleed media to edges; float controls above scrollable content.
- Place important items top and leading (start), accounting for RTL direction.
- Align elements to a shared grid; use alignment + indentation for hierarchy.
- Provide generous spacing around controls so targets don't crowd.
- Design the full layout first; collapse to compact/stacked only when it no longer fits.
- Don't change media aspect ratio to fit — scale and crop to keep key content visible.
- Respect safe areas and standard margins; account for cutouts and floating chrome.

**Accessibility**
- Web: reflow without horizontal scroll at 320px and 400% zoom.
- Adapt to large text — stacked layouts and fewer columns as text grows (Dynamic Type / font scaling).
- Preserve reading/DOM/semantic order to match visual order for screen readers and keyboard.
- Test across sizes, orientations, zoom, and both LTR/RTL.

**Avoid**
- Fixed-pixel layouts that don't reflow; controls jammed to edges without margins.
- Content hidden behind notches, status bars, or toolbars (ignoring safe-area insets).
- Abrupt layout jumps when resizing instead of smooth breakpoint changes.

**Full reference:** [Apple HIG](../../references/foundations/layout.md)
