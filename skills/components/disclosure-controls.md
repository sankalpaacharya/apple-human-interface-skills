# Disclosure Controls (Expand/Collapse)

> Controls that reveal or hide related information or functionality, keeping advanced or secondary content out of the way until it's needed.

**Use it for:** Progressively revealing advanced options or details (accordions, "Advanced Options"), or expanding nested hierarchy inline (folders, outline rows).

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<details>`/`<summary>`, or `<button aria-expanded aria-controls>` + region; trees use `role="treeitem"` + `aria-expanded` |
| SwiftUI | `DisclosureGroup`, or `List`/`OutlineGroup` for trees |
| Android (Compose) | Expandable `Column` with `AnimatedVisibility`; M3 has no built-in accordion |
| UIKit | `UITableView` collapsible sections, `UIStackView` toggling |
| React Native | Conditional render + `LayoutAnimation`, or RN Paper `List.Accordion` |
| Flutter | `ExpansionTile` / `ExpansionPanelList` |

**Guidelines**
- Hide details until relevant; keep most-used controls visible, tuck advanced behind disclosure.
- Provide a descriptive label saying what will be revealed, not a bare arrow.
- Disclosure triangle (inline hierarchy): points right collapsed, down expanded; on the leading edge.
- Disclosure button (section attached to a control): points down collapsed, up expanded; next to its content.
- Use at most one section-expanding disclosure button per view.
- Establish a clear visual relationship between toggle and revealed content.

**Accessibility**
- Web: toggle exposes `aria-expanded`; link to region via `aria-controls`; prefer `<details>`/`<summary>` for free keyboard + state.
- iOS VoiceOver / Android TalkBack: announce expanded/collapsed state and the label; tree nodes expose expanded state and Left/Right collapse/expand.
- Respect reduced-motion for expand/collapse animation.

**Avoid**
- Bare chevrons/arrows with no descriptive label.
- Multiple competing section-expanding buttons in one view.
- Expanded content visually far from its control.

**Full reference:** [disclosure-controls.md](../../references/components/disclosure-controls.md)
