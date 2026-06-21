# Accessibility

> Building interfaces everyone can perceive, operate, and understand regardless of ability or context.

**Use it for:** Always — it's a baseline for every screen, control, and flow, not an add-on feature.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Semantic HTML, ARIA roles/names, keyboard nav, `prefers-reduced-motion`/`prefers-contrast`; audit with axe/Lighthouse |
| SwiftUI | `.accessibilityLabel/Value/Hint`, `.accessibilityElement`, Dynamic Type, VoiceOver, `accessibilityReduceMotion` |
| Android (Compose) | `Modifier.semantics`, `contentDescription`, TalkBack, font scaling, `Modifier.clickable` roles |
| React Native | `accessibilityLabel`, `accessibilityRole`, `accessibilityState`, `AccessibilityInfo` (reduce-motion/screen-reader) |
| Flutter | `Semantics` widget, `Tooltip`, `MediaQuery.disableAnimations`/`textScaler`, `ExcludeSemantics` |

**Guidelines**
- Support text resizing to 200%+ without clipping; use relative units / Dynamic Type, never fixed heights for text.
- Meet contrast: 4.5:1 body text, 3:1 large text and UI components; test in light and dark.
- Convey state with more than color — add icons, labels, shapes (e.g. error icon plus message).
- Give touch targets ≥44pt with adequate spacing to prevent mis-taps.
- Provide captions, transcripts, and audio descriptions; never communicate critical info via audio alone.
- Don't autoplay media or auto-dismiss UI; let users control timing and opt out.

**Accessibility**
- Web: keyboard-operable with visible focus, semantic elements, `alt`/`aria-label` for icons, honor `prefers-reduced-motion`.
- iOS: meaningful VoiceOver labels, Dynamic Type, Reduce Motion/Transparency.
- Android: TalkBack `contentDescription`, font-scale support, accessible touch targets.
- Avoid content flashing >3×/sec; offer non-gesture alternatives to swipe/drag.

**Avoid**
- Relying on color alone for meaning or state.
- Tiny, tightly packed tap targets.
- Custom controls without roles, names, or keyboard support.
- Autoplaying/flashing media without controls or reduced-motion handling.

**Full reference:** [Apple HIG](../../references/foundations/accessibility.md)
