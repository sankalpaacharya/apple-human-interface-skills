# Sliders

> A slider is a track with a draggable thumb that people adjust between a minimum and maximum value.

**Use it for:** Selecting an approximate value from a continuous or stepped range (brightness, zoom, opacity). Pair with a number field/stepper when precision matters.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<input type="range" min max step>` (implicit `role="slider"`) with a `<label>` |
| SwiftUI | `Slider(value:in:step:)` |
| Android (Compose) | Material 3 `Slider` / `RangeSlider` |
| UIKit | `UISlider` |
| React Native | `@react-native-community/slider` |
| Flutter | `Slider` / `RangeSlider`; `CupertinoSlider` |

**Guidelines**
- Follow expected direction: minimum left, maximum right (bottom-to-top if vertical); fill the track from min to thumb.
- Add end icons or a label to convey what the slider controls.
- For wide ranges, supplement with a text field to type an exact value and/or stepper buttons.
- Give live feedback as the value changes (update preview/number in real time).
- Use `step`/tick marks to target specific values; labeling just min and max is often enough.
- Show the current value (tooltip or adjacent number) so it isn't hidden.

**Accessibility**
- Web: prefer native range; if custom, set `role="slider"` + `aria-valuenow/min/max` and `aria-valuetext`; Arrow/Page/Home/End keys; accessible name.
- iOS (VoiceOver): `UISlider`/`Slider` expose value and adjustable trait; set `accessibilityValue` for formatted values.
- Android (TalkBack): set `contentDescription`/`stateDescription`; slider is adjustable via TalkBack gestures.
- Thumb/target meets ≥44pt / 48dp for touch.

**Avoid**
- Reversing the conventional min/max direction.
- Sliders for exact-precision values without a paired numeric input.
- Custom sliders not operable by keyboard or exposing no value to assistive tech.

**Full reference:** [full reference](../../references/components/sliders.md)
