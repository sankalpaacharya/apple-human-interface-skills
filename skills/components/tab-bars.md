# Tab Bars (Primary / Bottom Navigation)

> A persistent bar of top-level destinations that lets people switch between the main sections of an app while preserving each section's state.

**Use it for:** Top-level navigation between a small number of peer sections (Home, Search, Profile) that must stay visible and quickly reachable.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<nav aria-label="Primary">` with `<a aria-current="page">` links, or `role="tablist"`/`tab`/`tabpanel` for in-page panels |
| SwiftUI | `TabView` with `.tabItem` (or `Tab` in newer APIs) |
| Android (Compose) | Material 3 `NavigationBar` + `NavigationBarItem` (bottom); `NavigationRail` on wide screens |
| UIKit | `UITabBarController` / `UITabBar` |
| React Native | `@react-navigation/bottom-tabs` (`createBottomTabNavigator`); RN Paper `BottomNavigation` |
| Flutter | `NavigationBar` (Material 3) / `BottomNavigationBar`; `CupertinoTabBar` |

**Guidelines**
- Use for navigation, not actions — put content commands in a toolbar.
- Keep the bar visible across sections; only hide it under a full-screen modal.
- Keep tabs small (≈5 or fewer); use a sidebar/drawer for complex hierarchies. Avoid overflow/"More" tabs.
- Keep tabs available even when a section is empty; explain emptiness inside, don't disable the tab.
- Include a short text label with each icon; use familiar, filled icons.
- Use a badge only for critical/new info; ensure label/active color has sufficient contrast.
- On wide screens consider promoting the tab bar to a sidebar/rail; collapse to bottom nav on narrow.

**Accessibility**
- Web: links mark active with `aria-current="page"`; in-page panels use the tabs pattern (`aria-selected`, roving tabindex, arrow keys, `aria-controls`); give the nav an `aria-label`.
- iOS (VoiceOver): `UITabBar`/`TabView` expose selected tab and index automatically.
- Android (TalkBack): `NavigationBarItem` announces selected state; set `contentDescription` on icons.
- Tap targets meet ≥44pt / 48dp; labels are not icon-only.

**Avoid**
- Disabling or hiding individual tab buttons (looks unstable).
- Using the bar for one-off actions instead of navigation.
- Icon-only tabs with no text labels.

**Full reference:** [full reference](../../references/components/tab-bars.md)
