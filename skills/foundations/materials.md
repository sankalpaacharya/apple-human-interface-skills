# Materials

> Translucent, blurred effects that separate a floating control/navigation layer from background content, creating depth while keeping foreground elements legible.

**Use it for:** Toolbars, nav/tab bars, sidebars, popovers, and sheets floating over scrolling content or media where the background should subtly peek through.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `backdrop-filter: blur()` + semi-transparent `background-color`; `@supports` gate + solid fallback |
| SwiftUI | `.background(.ultraThinMaterial / .regularMaterial / .thickMaterial)`, `.foregroundStyle(.secondary)` vibrancy |
| Android (Compose) | `Modifier.blur` / `RenderEffect` (API 31+) or scrim overlay; translucent `Surface` with fallback tint |
| React Native | `@react-native-community/blur` (`BlurView`) or `expo-blur`; solid fallback on unsupported targets |
| Flutter | `BackdropFilter(filter: ImageFilter.blur(...))` inside a `ClipRect`, semi-transparent overlay |

**Guidelines**
- Reserve translucency for the controls/navigation layer above content — not ordinary content backgrounds.
- Use it sparingly; over-applying blur distracts and hurts performance.
- Choose thickness by need: more opaque for text contrast, more translucent when context should show through.
- Use a regular/opaque treatment for text-heavy surfaces; clear/translucent only over rich media.
- Over bright media, add a dimming layer (~35% dark) to keep foreground legible; skip when already dark.
- Put vibrant, sufficiently opaque text/icons on top — thin gray content vanishes against blur.
- Always provide a solid fallback for platforms/browsers without backdrop blur.

**Accessibility**
- Honor reduce-transparency and increase-contrast settings by switching to a solid, opaque background.
- Verify text on translucent surfaces meets 4.5:1 against the worst-case background that can scroll behind.
- Don't rely on blur alone for separation — keep a border or shadow where contrast may be insufficient.

**Avoid**
- Translucency on content-layer backgrounds (confusing hierarchy).
- Low-contrast/non-vibrant text or icons over blurred materials.
- Blur with no opaque fallback, leaving unreadable bars.
- Heavy blur on many simultaneous elements (visual noise + jank).

**Full reference:** [Apple HIG](../../references/foundations/materials.md)
