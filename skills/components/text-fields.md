# Text Fields

> A text field is a rectangular area where people enter or edit a small, specific piece of text such as a name or email.

**Use it for:** Requesting a small, single piece of text (name, email, password). Use a multi-line variant for long input.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<input type="text\|email\|password\|tel\|url\|number">` with a `<label>`; `<textarea>` for multi-line |
| SwiftUI | `TextField` (`SecureField` for passwords; `TextField(axis: .vertical)` for multi-line) |
| Android (Compose) | Material 3 `TextField` / `OutlinedTextField` (`visualTransformation` for passwords) |
| UIKit | `UITextField` (single-line), `UITextView` (multi-line) |
| React Native | `TextInput` (`secureTextEntry`, `multiline`); RN Paper `TextInput` |
| Flutter | `TextField` / `TextFormField` (`obscureText`, `maxLines`); `CupertinoTextField` |

**Guidelines**
- Always pair each field with a visible label; placeholder text alone is not a label.
- Use placeholders only as supplementary hints ("e.g. name@site.com").
- Mask sensitive input (password type / `secureTextEntry` / `obscureText`).
- Size the field roughly to expected content; stack fields vertically with consistent widths and spacing.
- Set the right keyboard/input type (`email`, `tel`, `url`, `numeric` / `keyboardType`) so mobile shows the correct keyboard.
- Validate at the right moment: on blur for emails, inline as-you-type for username/password rules; show clear errors.
- Offer a clear ("×") button on touch/search-like fields; enable autofill (`autocomplete` / `textContentType` / `autofillHints`).

**Accessibility**
- Web: associate label and field via `<label for>`/wrapping; expose errors with `aria-invalid` + `aria-describedby`; logical tab order; visible focus.
- iOS (VoiceOver): set `accessibilityLabel`; field exposes Text Field trait and value.
- Android (TalkBack): set a `label`/`contentDescription`; errors via `error`/`semantics`.
- Field height meets ≥44pt / 48dp touch targets.

**Avoid**
- Using placeholder text as the only label.
- Masking input the user needs to verify, or blocking paste in password fields.
- Disabling autofill/autocomplete without reason.

**Full reference:** [full reference](../../references/components/text-fields.md)
