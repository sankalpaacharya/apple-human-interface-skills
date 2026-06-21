# Inclusion

> Putting people first by using respectful language and imagery and presenting content everyone can access and understand.

**Use it for:** Whenever you write copy, choose images, design forms, or localize.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Inclusive copy, diverse imagery (+`alt`), i18n/l10n (`lang`, `dir`, `Intl`), a11y baselines |
| SwiftUI | `String(localized:)` + String Catalogs, `Locale`/`AttributedString`, Dynamic Type, VoiceOver |
| Android (Compose) | `stringResource` + `res/values-<locale>`, `LocalLayoutDirection`, TalkBack, ICU plurals |
| React Native | `i18next`/`Intl`, `I18nManager` (RTL), accessible copy, locale-aware formatting |
| Flutter | `intl` + ARB files, `Localizations`, `Directionality`, `Semantics`, locale formatting |

**Guidelines**
- Use plain, direct language; address people as "you," reserve "we"/"our" for your company.
- Define or avoid technical terms; skip idioms and colloquialisms that don't translate.
- Be cautious with humor — subjective and hard to localize.
- Avoid unnecessary gender references; prefer gender-neutral nouns (also helps localization).
- If collecting gender, offer inclusive options and let people set pronouns.
- Represent diverse people in imagery; avoid stereotypes in roles and settings.
- Don't assume a narrow definition of "family," wealth, or shared cultural experience.
- Use people-first language about disability; respect how individuals self-identify.
- Build approachable experiences with clear interfaces and skippable onboarding.

**Accessibility**
- Inclusion requires accessibility — support screen readers, captions, keyboard, and customization across the disability spectrum (incl. temporary/situational).
- Internationalize: set language/direction, format dates/numbers/currency per locale, handle text expansion and RTL.
- Verify color symbolism per locale.

**Avoid**
- Jargon, idioms, and gendered language in UI copy.
- Stereotypical or homogeneous imagery.
- Assumptions baked into forms, defaults, and security questions.

**Full reference:** [Apple HIG](../../references/foundations/inclusion.md)
