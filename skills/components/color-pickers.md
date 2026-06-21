# Color Pickers

> A color picker (Apple "color well") lets people choose and adjust a color for text, shapes, or other elements.

**Use it for:** Picking or changing a color value, ideally via a native control for a familiar, low-effort experience.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<input type="color">` + `<label>`, or a custom `role="dialog"` popover with sliders/hex field |
| SwiftUI | `ColorPicker` |
| Android (Compose) | No M3 built-in; third-party color-picker composable or custom dialog |
| UIKit | `UIColorPickerViewController` / `UIColorWell` |
| React Native | `@react-native-community` / third-party color-picker libs |
| Flutter | `flutter_colorpicker` package or custom |

**Guidelines**
- Prefer the native control for a consistent, OS-integrated picker with minimal code.
- Show the currently selected color in the swatch/trigger so the active value stays visible.
- If custom, also offer a hex/RGB text field for exact values.
- Update previews live as the color changes.
- Provide a small set of recent/preset swatches when it speeds common choices.

**Accessibility**
- Web: native `<input type="color">` is keyboard- and SR-accessible; always give it a `<label>`.
- Don't rely on swatch color alone — expose the hex/value as text. iOS VoiceOver / Android TalkBack: label every control.
- Custom popovers: focus trap, Escape to close; targets ≥44pt / 48dp.

**Avoid**
- Reinventing a complex color UI when a native control suffices.
- Conveying the chosen color only visually with no text/value.
- Custom popovers without keyboard focus management.

**Full reference:** [color-wells.md](../../references/components/color-wells.md)
