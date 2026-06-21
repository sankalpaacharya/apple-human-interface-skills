# Split Views (Master–Detail / Multi-Pane Layout)

> A layout of two or three adjacent panes where selecting an item in one pane updates the contents of the next (e.g. list → detail).

**Use it for:** Showing multiple levels of hierarchy at once (sidebar/list + detail) on wide/regular-width screens with room for 2–3 columns.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | CSS grid/flex of `<section>` panes; list pane `<nav>`, detail `<main>`; draggable `role="separator"` with `aria-valuenow` |
| SwiftUI | `NavigationSplitView` (two/three columns); collapses to `NavigationStack` on compact |
| Android (Compose) | `ListDetailPaneScaffold` (Material 3 adaptive); `NavigationRail` + content |
| UIKit | `UISplitViewController` (`.doubleColumn` / `.tripleColumn`) |
| React Native | No core analog — custom flex layout, or `react-native-navigation` split; collapse to stack navigator on narrow |
| Flutter | Custom `Row` of `Expanded` panes / `TwoPane`; adaptive `NavigationRail` |

**Guidelines**
- Persistently highlight the current selection in each pane that leads to the detail.
- Use multi-pane only on wide layouts; on narrow/compact screens collapse to a single pane with drill-in navigation.
- For deep hierarchies use three panes (sidebar → list → detail); test all viewport widths.
- If panes are resizable, set sensible min/max sizes and keep the divider visibly grabbable; prefer a thin divider.
- Let people hide a pane (distraction-free editing) and provide multiple ways to restore it.
- Consider drag-and-drop between panes; a single overall title is usually enough.

**Accessibility**
- Web: resizable divider uses `role="separator"`, `tabindex="0"`, `aria-orientation`, `aria-valuenow/min/max`, arrow-key resize; convey selection via `aria-current`/`aria-selected`.
- iOS (VoiceOver): split view exposes columns; manage focus when collapsing list → detail.
- Android (TalkBack): pane scaffold announces pane changes; label each pane/region.
- Provide an accessible name for each pane; targets meet ≥44pt / 48dp.

**Avoid**
- Forcing multi-pane on compact/mobile widths (content wraps and truncates).
- Dividers so thin or panes so small the divider becomes unusable.
- Hiding a pane with no clear way to bring it back.

**Full reference:** [full reference](../../references/components/split-views.md)
