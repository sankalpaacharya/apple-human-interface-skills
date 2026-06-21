# Onboarding

> A fast, optional flow that helps people get a quick start using your app.

**Use it for:** When the app isn't fully self-explanatory, a feature needs setup/permission before it works, or you want to surface new features contextually.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Multi-step intro modals/carousels, product tours (Shepherd.js, Intro.js, Driver.js), gated by `localStorage`/user state |
| SwiftUI | `TabView(.page)` intro, `.sheet`/`.fullScreenCover` flow, `TipKit` contextual tips, `@AppStorage` gating |
| Android (Compose) | `HorizontalPager` intro, full-screen onboarding destination, coachmark overlays, DataStore gating |
| React Native | `react-native-onboarding-swiper`, `react-native-app-intro-slider`, tour libs (`rn-tourguide`) |
| Flutter | `introduction_screen`, `PageView` intro, `showcaseview` for tips, `shared_preferences` gating |

**Guidelines**
- Prefer letting people learn by doing; make onboarding interactive over read-only slides.
- Keep it brief, enjoyable, and skippable; don't force memorization.
- Favor context-specific tips near the relevant UI over one long upfront flow.
- If a tutorial is skippable, don't re-show it; keep it findable later (help/settings).
- Provide sensible defaults so people can start immediately; postpone non-essential setup.
- Tie permission requests to onboarding only when access is needed up front and you can explain the benefit.
- Let people experience the product before prompting for ratings, purchases, or accounts; don't block on large downloads.

**Accessibility**
- Make every step keyboard/switch navigable with a clear, focusable skip/dismiss control.
- Move focus to each step and announce it (dialog role + label / VoiceOver / TalkBack).
- Don't rely on hover-only coachmarks; ensure tips are reachable and dismissible without a pointer.

**Avoid**
- Long, mandatory tutorials that overwhelm or can't be skipped.
- Teaching standard OS/browser behavior instead of your app's value.
- Showing the same tour repeatedly or burying licensing/legal text in the flow.

**Full reference:** [full reference](../../references/patterns/onboarding.md)
