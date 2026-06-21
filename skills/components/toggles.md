# Toggles

> A toggle lets people choose between a pair of opposing states (on/off), using a distinct appearance for each state.

**Use it for:** A switch for turning a single setting on/off (applied immediately); a checkbox for opt-in/multi-select; radio buttons for 2–5 mutually exclusive options.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Switch: `<button role="switch" aria-checked>` or `<input type="checkbox" role="switch">`; checkbox: `<input type="checkbox">`; radios: `<input type="radio">` in `<fieldset>` |
| SwiftUI | `Toggle` (switch); `Toggle(...).toggleStyle(.checkbox)` on macOS; `Picker` for radio-style |
| Android (Compose) | `Switch`; `Checkbox` / `TriStateCheckbox`; `RadioButton` |
| UIKit | `UISwitch`; checkbox/radio via custom controls |
| React Native | `Switch` (core); RN Paper `Switch` / `Checkbox` / `RadioButton` |
| Flutter | `Switch`; `Checkbox`; `Radio`; `CupertinoSwitch` |

**Guidelines**
- Use a toggle only for state (on/off); for picking from a list use a select menu.
- Clearly identify what the toggle affects via a visible or programmatic label.
- Make the on/off difference obvious through shape/fill/checkmark, not color alone.
- Checkboxes support a mixed/indeterminate state for parent-of-group controls.
- Use a switch when the change applies instantly; a checkbox when changes apply on submit.
- Keep radio groups grouped (`<fieldset>`/`<legend>` or section) with consistent spacing.

**Accessibility**
- Web: switches need `role="switch"` + `aria-checked`; prefer native checkboxes/radios; provide an accessible name; Space toggles, arrows move within radio groups; group with `<fieldset>`/`<legend>`.
- iOS (VoiceOver): `UISwitch`/`Toggle` expose the Switch trait and on/off value.
- Android (TalkBack): `Switch`/`Checkbox` expose checked state; set a label.
- Hit target meets ≥44pt / 48dp; extend the tappable area to the label.

**Avoid**
- Using a switch to trigger an action rather than represent state.
- Conveying state with color only.
- A long list of radio buttons where a select menu fits better.
- Custom toggles built from plain views without role, state, or keyboard support.

**Full reference:** [full reference](../../references/components/toggles.md)
