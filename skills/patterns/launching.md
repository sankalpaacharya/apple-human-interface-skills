# Launching

> The startup experience from open to first interactive screen — ideally instant.

**Use it for:** Every page/app load is a launch moment to optimize. Use a splash/branding screen only briefly, not as an ad.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | First-paint perf: critical CSS, SSR/streaming, app-shell skeleton matching real layout, avoid FOUC/CLS |
| SwiftUI | Launch screen storyboard/asset (static, matches first screen), defer heavy work off the main thread, restore state |
| Android (Compose) | `SplashScreen` API (system, themed), avoid custom splash Activities, defer init |
| React Native | `react-native-bootsplash`/`expo-splash-screen` hidden once first screen is ready |
| Flutter | `flutter_native_splash` (native launch image), hide after first frame |

**Guidelines**
- Make it feel instant; people don't want to wait more than a second or two.
- Render an app shell / skeleton that closely matches the first real screen to avoid jarring flashes.
- Match the shell to the device's current theme and orientation.
- Avoid text in the placeholder shell (can't be localized, may flash on swap).
- Don't treat the load screen as a branding or "About" moment; keep it minimal.
- Restore previous state on return (scroll, open views, in-progress input) so people continue where they left off.
- Defer large/non-critical assets so the first screen is ready fast.

**Accessibility**
- Ensure the skeleton doesn't trap focus or announce noise; hide it from assistive tech until real content loads.
- Move focus to meaningful content once loaded; respect reduced-motion preferences for launch animation.

**Avoid**
- Splash screens or logos on every launch.
- Placeholder layouts that visibly shift when real content arrives.
- Blocking first render on large downloads.

**Full reference:** [full reference](../../references/patterns/launching.md)
