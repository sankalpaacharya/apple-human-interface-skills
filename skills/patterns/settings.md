# Settings

> A place for general, infrequently changed preferences that customize the experience.

**Use it for:** App-wide options (theme, account, defaults) people rarely change and that must persist across sessions. Task-level options belong inline, not here.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | A settings page/route persisted via `localStorage`/cookies or a user account; real form controls |
| SwiftUI | `Form`/`Settings` scene, `@AppStorage`/`UserDefaults`, `Toggle`/`Picker`; deep-link to iOS Settings app where relevant |
| Android (Compose) | Settings screen with Jetpack DataStore/`PreferenceDataStore`, `Switch`/`RadioButton` |
| React Native | Settings screen + `@react-native-async-storage`/MMKV, `Switch` |
| Flutter | Settings screen + `shared_preferences`, `settings_ui` package, `SwitchListTile` |

**Guidelines**
- Ship strong defaults that suit most people, so settings are optional; minimize their number.
- Keep task-specific options inline where they apply (filters, sort, show/hide), not buried in settings.
- Detect what you can (system dark mode, language, locale) instead of asking.
- Respect OS-level preferences (reduced motion, color scheme, contrast); don't duplicate or override them.
- Group related settings into clearly labeled sections; restore the last-viewed section when reopened.
- Make settings reachable in expected ways (clear menu/icon; consider a shortcut).

**Accessibility**
- Use real form controls (switches, selects) with associated labels.
- Group related controls (fieldset/legend or platform equivalents); reflect state via accessibility attributes.
- Announce when a setting is applied if there's no immediate visual confirmation.

**Avoid**
- Asking for setup info you can detect automatically.
- Redundant in-app copies of global system settings.
- Putting frequently used, contextual controls on a separate settings page.

**Full reference:** [full reference](../../references/patterns/settings.md)
