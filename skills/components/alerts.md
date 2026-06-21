# Alerts

> An alert is a modal dialog that delivers critical information and requires the user to respond before continuing.

**Use it for:** Warning before a destructive/irreversible action, confirming an important user-initiated action (e.g. a purchase), or reporting a problem the user must acknowledge.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<dialog role="alertdialog" aria-modal="true">` (never JS `alert()`/`confirm()`) |
| SwiftUI | `.alert(_:isPresented:)` |
| Android (Compose) | `AlertDialog` |
| UIKit | `UIAlertController` with `.alert` style |
| React Native | `Alert.alert(...)` |
| Flutter | `AlertDialog` via `showDialog` |

**Guidelines**
- Use sparingly — alerts interrupt; each must be essential and actionable.
- Don't alert merely to convey info, on load, or for common undoable actions.
- Write a clear, specific title (avoid "Error"); add message text only if it adds value.
- Use specific verb buttons ("Delete", "Erase") over "OK"; reserve "OK" for informational alerts.
- Put the default action on the trailing side, Cancel on the leading side; never make a destructive button the default.
- Style destructive buttons distinctly (e.g. red).

**Accessibility**
- Web: `role="alertdialog"`, focus the default/first focusable on open and restore on close, Escape cancels, background `inert`.
- iOS VoiceOver / Android TalkBack: announce as an interrupting dialog with its message.
- Touch targets ≥44pt / 48dp.

**Avoid**
- Using an alert when a menu of choices (action sheet) fits better.
- Long titles wrapping past two lines, or alerts that scroll.
- Overusing caution symbols.

**Full reference:** [alerts.md](../../references/components/alerts.md)
