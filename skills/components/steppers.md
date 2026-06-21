# Steppers

> A stepper is a two-segment control (increment/decrement) for changing a value by a fixed amount.

**Use it for:** Small, precise adjustments to a numeric value (quantity, copies). Pair with a text/number field when values vary widely.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<input type="number" step>` (native spinners) or a custom `role="spinbutton"` pair with `aria-valuenow/min/max` |
| SwiftUI | `Stepper(value:in:step:)` |
| Android (Compose) | No Material 3 stepper — compose two `IconButton`s (`Remove`/`Add`) around a value `Text` |
| UIKit | `UIStepper` |
| React Native | No core stepper — two `Pressable` buttons around a value; or a community stepper lib |
| Flutter | No Material stepper widget (`Stepper` is a wizard) — compose `IconButton`s; or `CupertinoButton` pair |

**Guidelines**
- Always show the value adjacent to the stepper; the buttons themselves don't display it.
- Pair with an editable number field so people can type large changes instead of many clicks.
- Define a sensible `step` plus `min`/`max` bounds; disable the relevant button at a limit.
- Consider a larger jump (e.g. 10×) on Shift-click for wide ranges.

**Accessibility**
- Web: prefer native `<input type="number">`; if custom, `role="spinbutton"` + `aria-valuenow/min/max` and an accessible name.
- iOS (VoiceOver): `UIStepper`/`Stepper` expose value and adjustable trait automatically.
- Android (TalkBack): give increment/decrement buttons `contentDescription` (e.g. "Increase quantity"), not just "+"/"−".
- Buttons keyboard-operable with a visible focus ring; each meets ≥44pt / 48dp target.

**Avoid**
- A stepper with no visible associated value.
- Forcing many clicks for large changes with no field to type into.
- Increment buttons lacking accessible names.

**Full reference:** [full reference](../../references/components/steppers.md)
