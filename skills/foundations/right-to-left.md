# Right to Left (RTL)

> Mirroring your interface to match the reading direction of RTL scripts like Arabic and Hebrew.

**Use it for:** Whenever you localize for Arabic, Hebrew, Persian, Urdu, or other RTL languages.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `dir="rtl"`/`dir="auto"`, CSS logical properties (`margin-inline-start`, `inset-inline`, `text-align: start`), `:dir()` |
| SwiftUI | Automatic via leading/trailing layout; `@Environment(\.layoutDirection)`, `.environment(\.layoutDirection, .rightToLeft)` |
| Android (Compose) | `LocalLayoutDirection`, start/end-based modifiers/padding, `supportsRtl` in manifest |
| React Native | `I18nManager.isRTL`, `start`/`end` style props, `writingDirection` |
| Flutter | `Directionality` widget, `EdgeInsetsDirectional`, `TextDirection`, start/end alignment |

**Guidelines**
- Prefer logical (start/end) layout over physical (left/right) so layout mirrors automatically.
- Align text to match interface direction; right-align in RTL contexts.
- Align a paragraph (3+ lines) by its own language, not the surrounding context.
- Use one consistent alignment for all items in a list, even mixed-script.
- Never reverse digit order within a number (phone, card); locale may swap numeral systems.
- Reverse the order of numerals showing progress/sequence to match a flipped control — but don't mirror the glyphs.
- Flip directional controls (sliders, progress, back/next) and reverse their start/end icons.
- Don't flip controls that point to a real direction or onscreen location.
- Reverse the order of images when their sequence is meaningful.

**Accessibility**
- Set direction correctly so screen readers announce reading order and bidi text renders; use auto-detection for user-generated content.
- Visually balance Arabic/Hebrew next to all-caps Latin (those scripts lack uppercase) — bump RTL font size slightly if needed.

**Avoid**
- Flipping photos, illustrations, logos, or universal marks (checkmark).
- Mirroring icons of real-world objects (clocks, right-handed tools) that aren't directional.
- Reversing digits inside a single number.

**Full reference:** [Apple HIG](../../references/foundations/right-to-left.md)
