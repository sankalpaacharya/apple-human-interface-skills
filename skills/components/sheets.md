# Sheets

> A sheet presents a focused, self-contained task closely related to the current context, layered over the page.

**Use it for:** Requesting specific input or completing a short, scoped task before returning (attach a file, choose a location). For long/complex multi-step flows, prefer a full-page route.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<dialog>` (`showModal()`) or a CSS bottom-sheet panel; `role="dialog"` + `aria-modal="true"` + `aria-labelledby` |
| SwiftUI | `.sheet(isPresented:)`; resizable via `.presentationDetents([.medium, .large])` |
| Android (Compose) | Material 3 `ModalBottomSheet` / `BottomSheetScaffold` |
| UIKit | `UISheetPresentationController` (detents); modal `present()` |
| React Native | `@gorhom/bottom-sheet`; `Modal` |
| Flutter | `showModalBottomSheet` / `DraggableScrollableSheet`; `showCupertinoModalPopup` |

**Guidelines**
- Show only one sheet at a time; close the current one before opening another.
- Always pair a Done/Save action with a Cancel/Close that dismisses without saving.
- Use Back for multi-step flows; never show Back, Cancel, and Done together.
- Cancel/Close on the leading (left) side; Done on the trailing (right) side.
- Pick a sensible default size; offer resize detents (medium vs full-height) only when useful.
- On mobile, support swipe-down to dismiss; show a drag grabber if resizable.
- If there are unsaved changes, confirm before discarding on dismiss.

**Accessibility**
- Web: trap focus, move focus to the sheet on open and restore on close; Escape dismisses; mark background `inert`.
- iOS (VoiceOver): sheets isolate focus automatically; ensure a labelled Close action.
- Android (TalkBack): modal bottom sheet scrims background; provide an accessible close/drag affordance.
- Drag/resize affordance has a keyboard/AT-operable equivalent; controls meet ≥44pt / 48dp targets.

**Avoid**
- Stacking sheets or opening one sheet from another without closing the first.
- A lone Done button as the only exit.
- Using a sheet for a prolonged editing task that deserves its own page/window.

**Full reference:** [full reference](../../references/components/sheets.md)
