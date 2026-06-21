# Entering Data

> Designing form input so people can supply information quickly and without mistakes.

**Use it for:** Any form, checkout, sign-up, settings, or search flow that collects user input.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<input>`/`<select>`/`<textarea>` with `type`, `autocomplete`, `inputmode`, `<label>`; Constraint Validation API or React Hook Form + Zod |
| SwiftUI | `TextField`/`SecureField`/`Picker`/`DatePicker`, `.keyboardType`, `.textContentType` for autofill |
| Android (Compose) | `TextField`/`OutlinedTextField` with `KeyboardOptions`, `autofill` semantics, `ExposedDropdownMenu` |
| React Native | `TextInput` (`keyboardType`, `textContentType`/`autoComplete`), `react-hook-form` |
| Flutter | `TextFormField`/`DropdownButtonFormField` with `Form` + validators, `keyboardType`, `autofillHints` |

**Guidelines**
- Pre-fill or auto-gather anything you already know (profile, location, prior entries); never ask for derivable data.
- Use autofill hints/content-type tokens (`email`, `name`, `cc-number`) so the platform can autofill.
- Pair every field with a visible label; use placeholders only as a format hint, never as the label.
- Prefill sensible defaults to reduce decisions, but never prefill a password field.
- Prefer choosing over typing (picker, segmented control, date picker) when options are finite.
- Set the right keyboard type/input mode for the field (email, tel, number, url); support paste.
- Validate inline as users type or on blur with specific, actionable errors; gate submit until required fields are valid.

**Accessibility**
- Associate labels and error messages with fields; mark invalid state programmatically (`aria-invalid` / `accessibilityInvalid` / VoiceOver / TalkBack hints).
- Announce validation errors via live region (`role="alert"`) or equivalent platform announcement.
- Don't convey required/error state by color alone — add text or icons.

**Avoid**
- Placeholder-as-label (disappears on focus, fails contrast).
- Forcing text entry where a picker would do.
- Prepopulating passwords or surfacing errors only after submit.

**Full reference:** [full reference](../../references/patterns/entering-data.md)
