# Popovers

> A popover is a transient view anchored to a control that appears above other content when clicked or tapped.

**Use it for:** Exposing a small amount of related info or a few quick actions tied to a trigger — dropdowns, editing pop-ups, contextual detail views — freeing space vs. a persistent panel.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `popover` attribute + Popover API (`popovertarget`); `role="menu"` or `role="tooltip"` per content |
| SwiftUI | `.popover(isPresented:)` |
| Android (Compose) | `Popup` / `DropdownMenu` (no exact M3 popover; bottom sheet on small screens) |
| UIKit | `UIPopoverPresentationController` |
| React Native | RN Paper `Menu`, or third-party popover libs |
| Flutter | `showMenu` / `Overlay` with `CompositedTransformFollower` |

**Guidelines**
- Keep contents small; limit to a few related tasks.
- Anchor the popover at the element that opened it; don't cover it or essential content.
- Auto-dismiss on outside tap or item selection; keep open for multi-select until explicit dismiss.
- Add a Close/Cancel/Done button only when it adds clarity.
- Show one popover at a time; never cascade popovers; render nothing over a popover except an alert.
- Size it just big enough for its contents; animate size changes smoothly.

**Accessibility**
- Web: Escape closes and returns focus to the trigger; tie trigger and popover via `aria-expanded`/`aria-controls`; manage focus for interactive content.
- iOS VoiceOver / Android TalkBack: announce as a popup; on narrow/mobile viewports use a full-screen sheet/modal instead.
- Touch targets ≥44pt / 48dp.

**Avoid**
- Using a popover for warnings or critical info (use an alert).
- Discarding user input when a non-modal popover is dismissed by outside tap.

**Full reference:** [popovers.md](../../references/components/popovers.md)
