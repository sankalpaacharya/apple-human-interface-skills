# Context Menus

> A context menu provides quick access to actions relevant to a specific item or view, revealed on demand (right-click / long-press).

**Use it for:** Frequently used actions tied to a specific item (a row, card, file, message), supplementing — never replacing — actions available elsewhere.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `role="menu"` popup on `contextmenu` (right-click) + long-press; trigger `aria-haspopup="menu"` |
| SwiftUI | `.contextMenu { ... }` |
| Android (Compose) | `DropdownMenu` shown on long-press (`combinedClickable`) |
| UIKit | `UIContextMenuInteraction` / `UIMenu` |
| React Native | Third-party (`react-native-context-menu-view`) or long-press ActionSheet |
| Flutter | `ContextMenuRegion` / `GestureDetector` onLongPress + `PopupMenuButton` |

**Guidelines**
- Include only the most relevant actions; keep the list short (~3 separator-delimited groups max).
- Always expose the same actions elsewhere — a context menu is hidden and not discoverable.
- Support it consistently across similar items; hide unavailable items rather than disabling (except Cut/Copy/Paste).
- Place the most frequent items first; rarely show a title.
- List destructive actions (Delete, Remove) last and style them distinctly.
- Don't show keyboard shortcuts here; provide either a context menu OR an inline edit menu, not both.

**Accessibility**
- Web: open on `contextmenu`/menu key + long-press; move focus in, arrow nav, Enter activate, Escape dismiss + restore focus; trigger `aria-haspopup="menu"`.
- iOS VoiceOver / Android TalkBack: expose the long-press action and menu items; mark destructive items by text, not color alone.
- Touch targets ≥44pt / 48dp.

**Avoid**
- Putting actions ONLY in a context menu.
- Long menus that scroll, or more than one submenu level.
- Relying on color alone to signal destructive actions.

**Full reference:** [context-menus.md](../../references/components/context-menus.md)
