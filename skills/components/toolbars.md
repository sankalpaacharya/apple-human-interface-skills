# Toolbars

> A horizontal bar of frequently used commands, controls, navigation, and search along the top (or bottom) edge of a view, acting on the current content.

**Use it for:** Actions that operate on the current view's content (edit, share, delete, new), and hosting the view title, back/navigation controls, and search.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<div role="toolbar" aria-label="…">` of `<button>`s; overflow `<button aria-haspopup="menu" aria-expanded>`; distinct from `<nav>` |
| SwiftUI | `.toolbar { ToolbarItem(placement:) }`; `Menu` for overflow |
| Android (Compose) | Material 3 `TopAppBar` / `BottomAppBar` with action `IconButton`s + overflow `DropdownMenu` |
| UIKit | `UIToolbar` (bottom) / `UINavigationBar` items; `UIBarButtonItem` |
| React Native | Header from `@react-navigation` (`headerRight`/`headerLeft`); RN Paper `Appbar` |
| Flutter | `AppBar` / `BottomAppBar` with `actions`; `PopupMenuButton` for overflow |

**Guidelines**
- Choose items deliberately to avoid overcrowding; define which move into an overflow ("More") menu as width shrinks. Don't overflow by default.
- Prioritize the most frequent actions; push secondary ones into overflow.
- Prefer recognizable icon buttons over text (except actions like "Edit"); use familiar standard icons.
- Group items logically (≤3 groups); keep grouping/placement consistent across pages/breakpoints.
- Position: leading = back / sidebar toggle / title; center = common controls; trailing = primary action, inspector toggles, search, overflow.
- Give one primary/prominent action only, on the trailing side; keep text-labeled buttons spaced apart.
- Use standard Back/Close controls and symbols; keep the title concise and never the app name.

**Accessibility**
- Web: `role="toolbar"` + `aria-label`; roving tabindex with arrow-key navigation; overflow trigger uses `aria-haspopup`/`aria-expanded`; icon-only buttons need labels + tooltips.
- iOS (VoiceOver): bar button items expose labels/traits; set `accessibilityLabel` on custom items.
- Android (TalkBack): set `contentDescription` on icon actions; overflow announces as a menu.
- Every toolbar action is also reachable via a menu/command; targets meet ≥44pt / 48dp.

**Avoid**
- Using a toolbar for primary section navigation (that's a tab bar/nav).
- More than three control groups, or running text labels together.
- Overcrowding the bar or adding an overflow menu when none is needed.

**Full reference:** [full reference](../../references/components/toolbars.md)
