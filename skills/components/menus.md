# Menus

> A menu reveals a list of commands, options, or states when the user activates a trigger, presenting actions in a space-efficient popup.

**Use it for:** Presenting commands or options tied to a button/trigger (dropdown, "More"/overflow menu), grouping related actions without consuming persistent screen space.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `role="menu"` + `role="menuitem"`, triggered by `<button aria-haspopup="menu" aria-expanded>` |
| SwiftUI | `Menu { ... }` (and `Picker` with `.menu` style) |
| Android (Compose) | `DropdownMenu` + `DropdownMenuItem` |
| UIKit | `UIMenu` on a `UIButton` / bar button item |
| React Native | RN Paper `Menu`, or `@react-native-menu/menu` |
| Flutter | `PopupMenuButton` / `MenuAnchor` |

**Guidelines**
- Write short, clear labels; verb for actions (View, Delete); Title Case, drop articles.
- Append an ellipsis (…) when an item needs more input (e.g. "Export…").
- List important/frequent items first; group related items with a divider.
- Use icons sparingly and consistently — all items in a group get one, or none do.
- Show unavailable items as disabled, not removed; keep the menu openable even if all disabled.
- Use submenus sparingly (one level, ~5 items); for toggles use one item with a changing label or checkmark.
- Keep menus short; scrolling menus only for dynamic/user-generated content.

**Accessibility**
- Web: trigger `aria-haspopup="menu"` + `aria-expanded`; arrow nav (roving tabindex), Enter/Space activate, Escape close + return focus; `menuitemcheckbox`/`menuitemradio` with `aria-checked`.
- iOS VoiceOver / Android TalkBack: announce menu, items, checked/disabled state.
- Touch targets ≥44pt / 48dp.

**Avoid**
- Using a menu for primary navigation when persistent visibility matters.
- More than one level of submenu.
- Mismatched icon treatment within a group; mouse-only interaction.

**Full reference:** [menus.md](../../references/components/menus.md)
