# Combo Boxes

> A combo box combines a text field with a dropdown list, so people can type a custom value or pick from predefined options.

**Use it for:** Letting people type a free-form value or choose from likely options — autocomplete and filterable suggestion lists. Use a plain select when only predefined options are valid.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<input>` + `<datalist>`, or ARIA combobox (`role="combobox"` + `role="listbox"`) |
| SwiftUI | `TextField` + suggestion list, or `.searchable` with completions |
| Android (Compose) | `ExposedDropdownMenuBox` with editable `TextField` |
| UIKit | `UITextField` + `UITableView` suggestions, or `UISearchController` |
| React Native | Third-party autocomplete (`react-native-autocomplete-input`) |
| Flutter | `Autocomplete` / `RawAutocomplete`, or `DropdownMenu` (editable) |

**Guidelines**
- Populate with a meaningful default value that hints at the hidden choices.
- Use a visible label so people know what kind of items to expect.
- Offer relevant choices while still allowing a custom typed value; filter as the user types.
- Keep list items no wider than the field so they don't truncate awkwardly.
- Remember typed custom values aren't added to the predefined list.

**Accessibility**
- Web: prefer `<input>`+`<datalist>`; else full ARIA combobox (`aria-expanded`, `aria-controls`, `aria-activedescendant`).
- Full keyboard support: arrows to move, Enter to choose, Escape to close, typing to filter.
- iOS VoiceOver / Android TalkBack: announce expanded state and active option; associate a label; targets ≥44pt / 48dp.

**Avoid**
- A custom combobox missing keyboard navigation or state.
- Hiding the affordance that suggestions exist.
- List items wider than the input that get truncated.

**Full reference:** [combo-boxes.md](../../references/components/combo-boxes.md)
