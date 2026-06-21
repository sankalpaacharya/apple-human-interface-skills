# Action Sheets

> An action sheet presents a set of choices related to an action the user just initiated, typically from the screen edge.

**Use it for:** Offering several related choices after an intentional action (e.g. "Discard" / "Save" on cancel), especially to confirm a destructive action while giving alternatives. Prefer over an alert when more than confirm/cancel is needed.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<dialog>` rendered as a bottom sheet, or `role="menu"` with `menuitem`s |
| SwiftUI | `.confirmationDialog` (formerly `ActionSheet`) |
| Android (Compose) | `ModalBottomSheet` with action rows |
| UIKit | `UIAlertController` with `.actionSheet` style |
| React Native | `ActionSheetIOS` / `@expo/react-native-action-sheet` |
| Flutter | `showCupertinoModalPopup` + `CupertinoActionSheet`, or `showModalBottomSheet` |

**Guidelines**
- Use after a user-initiated action; use a menu when the user explicitly opens one.
- Keep titles short (ideally one line); add a message only when needed.
- Provide a Cancel button (at the bottom) when an action might destroy data.
- Style destructive choices prominently and place them at the top.
- Keep choices few (~3 plus Cancel) so the sheet doesn't scroll.

**Accessibility**
- Web: trap focus on open, restore to trigger on close; Escape/outside-tap dismiss as Cancel; mark background `inert`.
- iOS VoiceOver / Android TalkBack: announce as a modal; destructive items get a name stating the consequence — not color alone.
- Touch targets ≥44pt / 48dp.

**Avoid**
- Letting the sheet scroll (causes accidental taps).
- Announcing a problem unprompted (that's an alert's job).

**Full reference:** [action-sheets.md](../../references/components/action-sheets.md)
