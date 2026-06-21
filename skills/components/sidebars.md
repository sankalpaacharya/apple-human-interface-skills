# Sidebars (Side Navigation / Drawer)

> A panel on the leading (left) side of a view for navigating between app areas or top-level content collections like folders and playlists.

**Use it for:** Apps with more sections than fit a tab bar, or with nested collections, on wide layouts (desktop/tablet) where space allows persistent navigation.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<nav aria-label="Sidebar">` with links (`aria-current`); `<details>`/`role="tree"` for groups; off-canvas drawer on narrow screens |
| SwiftUI | `NavigationSplitView` sidebar column; `List` with `Section`/`DisclosureGroup` |
| Android (Compose) | Material 3 `ModalNavigationDrawer` / `PermanentNavigationDrawer` + `NavigationDrawerItem` |
| UIKit | `UISplitViewController` primary column; `UICollectionView` list sidebar |
| React Native | `@react-navigation/drawer` (`createDrawerNavigator`) |
| Flutter | `Drawer` / `NavigationDrawer` (Material 3); `NavigationRail` on wide screens |

**Guidelines**
- Prefer a tab bar first when sections are few; reach for a sidebar when the hierarchy is broader.
- Let people customize ordering/contents when feasible; use collapsible disclosure groups for long lists.
- Show at most ~2 levels of hierarchy; deeper structures belong in a split view (sidebar → list → detail).
- Use succinct group titles and familiar icons; keep icon color purposeful (default to one accent).
- Persistently highlight the current selection.
- Let people hide/show the sidebar, but don't hide it by default — keep it discoverable; collapse to a drawer when the viewport narrows.
- Avoid placing critical actions at the very bottom (can be cut off).

**Accessibility**
- Web: `<nav>` with a unique `aria-label`; `aria-current="page"`; `aria-expanded` on group toggles; drawer toggle uses `aria-expanded`/`aria-controls` and traps focus when modal.
- iOS (VoiceOver): split-view sidebar exposes selection; label rows and disclosure controls.
- Android (TalkBack): drawer items expose selected state; set `contentDescription` on icons.
- Drawer toggle and rows meet ≥44pt / 48dp targets.

**Avoid**
- Forcing a sidebar in cramped layouts where a tab bar fits better.
- More than two levels of nesting inline.
- Hiding the sidebar by default with no obvious way to reveal it.

**Full reference:** [full reference](../../references/components/sidebars.md)
