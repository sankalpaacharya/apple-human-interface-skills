# Modality

> Content shown in a dedicated mode that blocks interaction with the rest of the app until explicitly dismissed.

**Use it for:** Critical info people must act on, confirming a recent action, a short self-contained task, or an immersive/focused experience (media viewer, editor).

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<dialog>` + `showModal()`, or `role="dialog"`/`role="alertdialog"` with focus trap + backdrop; sheets/drawers |
| SwiftUI | `.sheet`/`.fullScreenCover`, `.alert`/`.confirmationDialog`, `.presentationDetents` for sheets |
| Android (Compose) | `ModalBottomSheet`, `Dialog`/`AlertDialog`, full-screen destination |
| React Native | `Modal` component, `@react-navigation` modal stack, `@gorhom/bottom-sheet` |
| Flutter | `showModalBottomSheet`, `showDialog`/`AlertDialog`, full-screen route |

**Guidelines**
- Use modality only when there's a clear benefit; it interrupts and demands dismissal.
- Keep modal tasks simple, short, and single-path; avoid deep nested hierarchies.
- Use a full-screen modal for in-depth/complex tasks (media, markup, editing).
- Always provide an obvious dismiss control (close button, Escape/back, backdrop where safe).
- Confirm before closing if unsaved content would be lost; offer save/cancel.
- Give the modal a clear title naming its task; show only one modal at a time. Never stack alerts.

**Accessibility**
- Mark as a modal dialog with an accessible title (`aria-modal`/`aria-labelledby` / VoiceOver / TalkBack equivalents).
- Trap focus inside, move focus in on open, and return focus to the trigger on close.
- Support Escape/back to dismiss; use alert-dialog role for confirmations needing acknowledgment.

**Avoid**
- Overusing modals for non-critical info or routine status.
- No-dismiss or hard-to-find close affordances.
- Multiple simultaneous overlapping modals that bury prior context.

**Full reference:** [full reference](../../references/patterns/modality.md)
