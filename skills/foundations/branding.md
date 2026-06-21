# Branding

> Expressing a recognizable brand identity while keeping the experience familiar and content-first.

**Use it for:** Establishing a product's visual and verbal identity (accent color, brand type, voice) across a site or app without crowding out content.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Design tokens (CSS custom properties for accent), `@font-face`/variable fonts, consistent copy voice |
| SwiftUI | `Color` accent + `.tint()`, asset catalog brand colors, custom `Font`, `AccentColor` asset |
| Android (Compose) | `ColorScheme` primary/brand colors in `MaterialTheme`, custom `FontFamily` in `Typography` |
| React Native | Theme context / token object for accent, custom fonts via `useFonts`, shared `StyleSheet` |
| Flutter | `ThemeData` `colorScheme.primary`, `TextTheme` with custom `fontFamily`, `Theme` widget |

**Guidelines**
- Carry a consistent brand voice and tone through all copy.
- Expose the accent color as a token and apply it to primary actions, links, and highlights.
- Use a brand font for headlines if desired, but keep it legible at all sizes; pair with a reliable system font for body.
- Keep branding subordinate to content; don't plaster logos throughout — users know which app they're in.
- Use standard, familiar UI patterns and locations even within a stylized design.
- Don't treat a loading/splash screen as a branding moment; put brand expression in onboarding/welcome.
- Respect third-party trademark guidelines (e.g. don't misuse Apple marks).

**Accessibility**
- Brand colors must still meet contrast (4.5:1 text, 3:1 UI/large text) in light and dark.
- Custom fonts must support heavier weights and scale with Dynamic Type / font scaling / browser zoom.
- Provide accessible text alternatives for any text rendered as brand imagery.

**Avoid**
- Logo and brand chrome that crowds out content.
- Illegible brand fonts or fonts that don't scale.
- Using a launch/splash screen to deliver brand messaging.

**Full reference:** [Apple HIG](../../references/foundations/branding.md)
