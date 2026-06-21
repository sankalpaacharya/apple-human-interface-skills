# Focus and Selection

> Focus visually marks the element an interaction targets; selection marks the item(s) a user has chosen to act on.

**Use it for:** Every keyboard- or remote-navigable interface; lists, grids, menus, and tabs needing arrow-key navigation; modals and dynamic views where focus must move or restore.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `:focus-visible`, `element.focus()`, `tabindex` + roving tabindex, `aria-selected`/`aria-current`, `::selection` |
| SwiftUI | `@FocusState` + `.focused`, `.focusable`, `.defaultFocus`, `List`/`Table` `selection:`, `.textSelection` |
| Android (Compose) | `FocusRequester` + `Modifier.focusRequester`/`onFocusChanged`, `Modifier.selectable`/`selectableGroup`, `SelectionContainer` |
| React Native | `ref.focus()`, `focusable`/`hasTFocus` (TV/desktop), `accessibilityState={{selected}}`, `selectable` text |
| Flutter | `Focus`/`FocusNode` + `FocusScope`, `FocusTraversalGroup`, `SelectableText`/`SelectionArea`, selection state |

**Guidelines**
- Rely on native focus behavior wherever possible; build custom handling only when necessary.
- Never move focus without a user action — except to keep it sensible when the focused element is removed.
- On opening a modal/dialog, move focus into it; on close, restore focus to the triggering element.
- Use a focus ring for text fields and single controls; a row/cell highlight for items in a list or collection.
- Make focus order follow reading order; group related controls so arrow keys stay within a logical area (roving tabindex / focus group).
- Distinguish focus from selection: focusing an item shouldn't auto-activate it if that causes a disruptive shift; require explicit Enter/Space/tap.
- Reflect selection state programmatically (`aria-selected`, `selected` accessibility state) and style selected items distinctly from focused ones.

**Accessibility**
- Always keep a clearly visible focus indicator (web/desktop: `:focus-visible`); never remove without an equally visible replacement.
- Ensure the indicator has sufficient contrast and isn't clipped by overflow or occluding elements.
- Manage focus in dynamic UI (route changes, panels) so it never lands on a hidden element or gets lost; announce changes to VoiceOver/TalkBack.
- Keep text selectable with adequate contrast; don't disable selection on readable content.

**Avoid**
- Removing or suppressing focus outlines, leaving keyboard users unable to see where they are.
- Programmatically stealing or resetting focus during a user's task.
- Auto-selecting/activating a focused item when it triggers a jarring context shift.
- Conveying selection only by color with no programmatic state for assistive tech.

**Full reference:** [full reference](../../references/inputs/focus-and-selection.md)
