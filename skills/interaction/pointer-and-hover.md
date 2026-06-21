# Pointer and Hover

> Mouse and trackpad input for precise navigation, hover feedback, and contextual (right-click) actions.

**Use it for:** Desktop/laptop and hybrid experiences where users expect precision, hover-revealed controls (tooltips, row actions), and right-click context menus.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `:hover`, `:focus-visible`, Pointer Events (`pointerdown`/`pointermove`), `contextmenu`, CSS `cursor` |
| SwiftUI | `.hoverEffect`, `.onHover`, `.contextMenu`, `.pointerStyle`, `.help` (tooltip) |
| Android (Compose) | `Modifier.hoverable` / `interactionSource`, `Modifier.pointerHoverIcon`, `TooltipBox`, long-press context menu |
| React Native | `Pressable` `onHoverIn`/`onHoverOut`, `onLongPress`, `cursor` style (web/desktop) |
| Flutter | `MouseRegion` (`onEnter`/`onExit`, `cursor`), `Tooltip`, `GestureDetector.onSecondaryTap` |

**Guidelines**
- Give interactive elements clear hover feedback (subtle background, tint, or elevation).
- Set appropriate cursors: pointer on clickable elements, I-beam on text, resize on draggable edges.
- Keep hover effects meaningful — a hover change should signal something is interactive.
- Make hit targets comfortable: pad clickable areas beyond their visible bounds.
- Keep adjacent hit regions contiguous (e.g. toolbar buttons) to avoid flicker.
- Behave consistently across input modes; pair every hover affordance with a focus equivalent.
- Reserve scaling/elevation hover for elements with room to grow; use tint-only for tightly packed items.

**Accessibility**
- Never make functionality hover-only — revealed content/actions must also appear on keyboard focus and be reachable by touch.
- Provide a keyboard/touch-accessible alternative to right-click context menus (visible "more" button or context-menu key).
- Use focus-visible semantics so rings show for keyboard users without flashing on every click.
- Ensure hit targets are large enough (~44pt/dp) for limited motor precision; VoiceOver/TalkBack reach the same actions.

**Avoid**
- Hover-only menus, tooltips, or controls with no keyboard/touch path.
- Removing default cursors or focus outlines without a replacement.
- Gratuitous, purely decorative pointer/hover effects.
- Overriding native scroll, swipe-between-pages, or zoom gestures.

**Full reference:** [full reference](../../references/inputs/pointing-devices.md)
