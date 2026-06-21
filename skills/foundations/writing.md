# Writing

> The words in your interface — labels, messages, empty states, errors — are a core part of the user experience.

**Use it for:** Any microcopy: buttons, links, alerts, errors, settings, empty states, onboarding.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | UI copy, button/link text, form labels/placeholders, error/empty-state messaging; ties into a11y + i18n |
| SwiftUI | `Text`/`Label` strings, `String(localized:)` + String Catalogs, `LocalizedStringKey` |
| Android (Compose) | `stringResource` from `strings.xml`, plurals/`quantityString`, `res/values-<locale>` |
| React Native | `<Text>` content via i18n keys (`i18next`/`Intl`), localized strings |
| Flutter | `Text` via `intl`/ARB localization, `AppLocalizations` |

**Guidelines**
- Define a consistent voice and vary tone to match the situation (serious for errors, light for wins).
- Be clear and concise; cut unneeded words and read copy aloud to test it.
- Write action-oriented labels with verbs ("Send," "Save"); avoid cute or vague labels.
- Use descriptive link/button text ("Learn more about pricing"), never "Click here" — critical for screen readers.
- Pick title case or sentence case per element type and apply it uniformly; reuse language patterns.
- Label multi-step flows consistently ("Get Started" → "Continue" → "Done").
- Use possessive pronouns sparingly; avoid "we" in errors — prefer "Unable to load content."
- Match terms to the input ("tap" on touch, "click" with a pointer).
- Give empty states a clear next action; don't put crucial info there since it disappears.
- Write helpful errors near the problem — say what to do, avoid blame and "oops"/"uh-oh."

**Accessibility**
- Descriptive link/button text is essential for screen-reader users navigating by controls.
- Always pair form fields with visible labels; placeholder text is not a label substitute.
- Write with localization in mind: plain language, no jargon or gendered terms.

**Avoid**
- "Click here" and vague labels.
- Robotic errors ("Invalid name") and blame-y or insincere tone.
- Placeholder-only fields with no real label.

**Full reference:** [Apple HIG](../../references/foundations/writing.md)
