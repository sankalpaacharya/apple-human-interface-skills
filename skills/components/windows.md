# Windows

> A window is the bounded surface that presents an app's content; on the web it maps to the browser viewport, and on mobile to the device screen / scene.

**Use it for:** The primary surface where main navigation and content live; auxiliary surfaces (compose, detail, settings) map to modals, panels, or new windows/scenes when multitasking helps.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Browser viewport/tab (responsive layout); `window.open()` / modals for auxiliary; PWA standalone window |
| SwiftUI | `WindowGroup` / `Window` (macOS/iPadOS); a single scene fills the screen on iOS |
| Android (Compose) | `Activity` window; adapt with `WindowSizeClass`; multi-window / split-screen support |
| UIKit | `UIWindow` / `UIWindowScene`; `UISceneSession` for multiple scenes |
| React Native | Single root view per app; size adapts via `Dimensions`/`useWindowDimensions` |
| Flutter | Single `FlutterView` / `MediaQuery`-driven layout; desktop multi-window is emerging |

**Guidelines**
- Make layouts adapt fluidly across sizes (size classes / breakpoints) to support resizing and multi-window/multitask use.
- Open a new window/tab/scene only when it genuinely helps; excessive ones create clutter.
- Offer "open in new window" as an explicit option rather than default behavior.
- Set sensible min/max sizes and breakpoints so the layout never breaks at extremes.
- Don't fake native window chrome/controls; rely on the platform's real frame.
- Account for system-provided overlays (safe areas / insets, PWA title-bar area) and inset accordingly.

**Accessibility**
- Web: preserve logical focus and reading order as layout reflows; give programmatically-opened windows a descriptive `<title>` and move focus; usable at high zoom and small viewports.
- iOS (VoiceOver): each scene exposes its content; manage focus when presenting new scenes.
- Android (TalkBack): announce window/Activity transitions; keep content reachable across configuration changes.
- Nothing becomes unreachable or clipped across sizes; controls meet ≥44pt / 48dp targets.

**Avoid**
- Opening new windows/tabs/scenes as default behavior.
- Custom window frames or controls that imitate the OS.
- Layouts that overlap or clip UI at extreme sizes.

**Full reference:** [full reference](../../references/components/windows.md)
