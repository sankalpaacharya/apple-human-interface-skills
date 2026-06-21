# Pickers

> A picker presents one or more scrollable lists of distinct values to choose from, including date and time pickers.

**Use it for:** Choosing from a medium-to-long list of predictable, logically ordered values. Use native date/time inputs for dates and times; a select for short lists; a searchable list for very large sets.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<input type="date\|time\|datetime-local\|month">`; `<select>` or ARIA `listbox` for value lists |
| SwiftUI | `DatePicker`, `Picker` (`.wheel`/`.menu` styles) |
| Android (Compose) | `DatePicker`/`TimePicker`, `DropdownMenu` for value lists |
| UIKit | `UIDatePicker`, `UIPickerView` |
| React Native | `@react-native-community/datetimepicker`, `@react-native-picker/picker` |
| Flutter | `showDatePicker`/`showTimePicker`, `CupertinoPicker`, `DropdownButton` |

**Guidelines**
- Use predictable, logically ordered values (alphabetical, chronological) for quick scanning.
- Show the picker in context, near the field being edited, rather than navigating to a new view.
- Prefer native date/time controls — they bring calendar UI, keyboard entry, and localization for free.
- Let the locale format and order date/time parts; don't hardcode order.
- For minute granularity, constrain intervals (e.g. 15-minute steps).

**Accessibility**
- Web: native date/time and `<select>` are keyboard- and SR-accessible — prefer them; give every picker a `<label>`.
- iOS VoiceOver / Android TalkBack: native pickers expose adjustable values; custom listboxes need roles, arrow nav, and selected state.
- Touch targets ≥44pt / 48dp.

**Avoid**
- Recreating iOS scrolling wheel pickers in the browser.
- Switching to a separate screen just to show the picker.
- Custom date widgets that lack keyboard support or localization.

**Full reference:** [pickers.md](../../references/components/pickers.md)
