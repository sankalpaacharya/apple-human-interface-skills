# Icons (Interface Icons / Glyphs)

> Simple graphic symbols that express a single action, item, or mode in a way people instantly understand.

**Use it for:** Toolbar/menu/button actions and labeling content where a recognizable glyph reads faster than text.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Inline `<svg>` or sprite/library (Lucide, Heroicons); `currentColor`, `aria-label`/`aria-hidden` |
| SwiftUI | `Image(systemName:)` (SF Symbols), `.symbolRenderingMode`, `.accessibilityLabel` |
| Android (Compose) | `Icon(imageVector = Icons.…)` (Material Icons) with `contentDescription`, `tint` |
| React Native | `react-native-vector-icons` / SVG components, `accessibilityLabel` on the touchable |
| Flutter | `Icon(Icons.…)` (Material) or `SvgPicture`, `semanticLabel`, `color` |

**Guidelines**
- Keep designs simplified and recognizable; use familiar metaphors tied to the action.
- Maintain consistency across the set — same size, detail, stroke weight, perspective.
- Match icon stroke weight to adjacent text weight unless intentionally emphasizing one.
- Optically center asymmetric icons rather than geometric centering.
- Use vector formats so icons scale crisply and adapt to `currentColor`/`tint`.
- Drive selected/unselected states with color/fill, not separate art.
- Use inclusive, gender-neutral imagery; localize and flip directional glyphs for RTL.
- Reuse standard glyphs (search = magnifier, delete = trash, share, more = ellipsis, add = plus).
- Avoid depicting Apple hardware (dates quickly; trademark risk).

**Accessibility**
- Icon-only controls need an accessible name (`aria-label` / `contentDescription` / `accessibilityLabel`).
- Mark purely decorative icons as hidden so they aren't announced.
- Ensure icon contrast meets 3:1 against its background.

**Avoid**
- Overly detailed glyphs that blur at small sizes.
- Mixing stroke weights, sizes, or perspectives across a set.
- Unlabeled icon buttons.

**Full reference:** [Apple HIG](../../references/foundations/icons.md)
