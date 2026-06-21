# Select Menus

> A select menu (Apple "pop-up button") displays a menu of mutually exclusive options and updates to show the current selection.

**Use it for:** Choosing one value from a flat list of mutually exclusive options, saving space when you don't need all options visible. Use a menu/button list for actions, multi-select, or submenus.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<select>` + `<option>`/`<optgroup>` with a `<label>`; ARIA combobox/listbox if custom-styled |
| SwiftUI | `Picker(...).pickerStyle(.menu)` (pop-up button); `Menu` for richer menus |
| Android (Compose) | Material 3 `ExposedDropdownMenuBox` + `DropdownMenu` |
| UIKit | `UIButton` with `UIMenu` (pull-down/pop-up menu) |
| React Native | `@react-native-picker/picker`; RN Paper `Menu` |
| Flutter | `DropdownMenu` / `DropdownButton`; `CupertinoPicker` |

**Guidelines**
- Provide a useful default that hints at the choices; make it the most likely value.
- Give context with a visible label so people can predict options without opening it.
- Keep the option list flat and mutually exclusive; group with `<optgroup>`/sections.
- Use a select for moderate lists; for very long lists prefer a searchable combobox.
- Optionally include a "Custom…" option to reveal extra inputs only when needed.
- Don't use a select for triggering actions — use buttons/menus.

**Accessibility**
- Web: prefer native `<select>` (keyboard- and screen-reader-friendly); always associate a `<label>`; if custom, implement the full ARIA combobox pattern.
- iOS (VoiceOver): native pickers/menus expose current value and options automatically.
- Android (TalkBack): exposed dropdown announces selection; label the field via `contentDescription`/label.
- Control meets ≥44pt / 48dp target with a visible focus ring.

**Avoid**
- Custom dropdowns that don't replicate native keyboard behavior.
- Using a select for multi-select or for actions.
- Empty or meaningless default values when a sensible default exists.

**Full reference:** [full reference](../../references/components/pop-up-buttons.md)
