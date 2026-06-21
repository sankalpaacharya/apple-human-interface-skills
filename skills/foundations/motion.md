# Motion

> Purposeful, fluid animation that conveys status, gives feedback, and enriches the experience — without distracting or causing discomfort.

**Use it for:** Feedback tied to a user action, transitions that clarify spatial relationships (open/close, expand/collapse), and subtle emphasis on state changes.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | CSS transitions/animations + Web Animations API; transform/opacity; gate with `prefers-reduced-motion` |
| SwiftUI | `withAnimation`/`.animation`, `matchedGeometryEffect`, transitions; `accessibilityReduceMotion` |
| Android (Compose) | `animate*AsState`, `AnimatedVisibility`, `updateTransition`; check `Settings` animator scale / reduce-motion |
| React Native | `Animated`/`LayoutAnimation`/Reanimated; `AccessibilityInfo.isReduceMotionEnabled()` |
| Flutter | `AnimatedContainer`, `AnimationController`, `Hero`; `MediaQuery.disableAnimations` |

**Guidelines**
- Add motion purposefully; skip gratuitous animation that distracts or disorients.
- Keep feedback animations brief and precise so they feel lightweight.
- Make motion mirror the gesture: a view entering from the top should leave toward the top.
- Avoid animating frequent, repeated interactions; let platform defaults handle routine UI.
- Never block input on an animation — let people cancel or act before it finishes.
- Animate cheap properties (transform, opacity) targeting ~60fps; avoid animating layout.
- Use animated symbols/icons only where they add meaning.
- Provide non-motion alternatives for anything important conveyed by animation.

**Accessibility**
- Respect reduce-motion across platforms (`prefers-reduced-motion`, Reduce Motion, animator scale) — replace large/parallax motion with instant or simple fades.
- Never make motion the only channel for essential info.
- Avoid flashing/oscillating effects (>3×/sec).
- Ensure motion doesn't trap focus or delay keyboard interaction.

**Avoid**
- Animation for its own sake, or on high-frequency interactions.
- Motion that contradicts the triggering gesture's direction.
- Blocking interaction until an animation completes.
- Ignoring reduce-motion, or flashing/looping oscillation that can cause discomfort.

**Full reference:** [Apple HIG](../../references/foundations/motion.md)
