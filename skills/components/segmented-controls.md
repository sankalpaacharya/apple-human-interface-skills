# Segmented Controls

> A segmented control is a linear set of two or more equal-width segments, each acting as a button, offering a single choice from a related set.

**Use it for:** A single choice among closely related, mutually exclusive options, or switching between subviews within the same section (use a tab bar for top-level sections).

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `role="tablist"`/`role="tab"` (view switch) or a styled radio group; toggle buttons with `aria-pressed` (multi-select) |
| SwiftUI | `Picker(...).pickerStyle(.segmented)` |
| Android (Compose) | Material 3 `SingleChoiceSegmentedButtonRow` / `MultiChoiceSegmentedButtonRow` |
| UIKit | `UISegmentedControl` |
| React Native | `@react-native-segmented-control/segmented-control`; RN Paper `SegmentedButtons` |
| Flutter | `SegmentedButton` (Material 3); `CupertinoSegmentedControl` / `CupertinoSlidingSegmentedControl` |

**Guidelines**
- Keep all segments equal width and visually balanced; keep icon/title widths consistent.
- Limit to about 5 segments on narrow layouts, up to ~5–7 on wide ones.
- Use either all text or all icons in one control, not a mix; nouns/noun phrases for labels.
- Keep one consistent behavior per control: all segments select state, or all perform actions — never mix.
- For icon-only segments, provide tooltips/labels clarifying each meaning.
- For switching whole app sections, use a tab bar/navigation instead.

**Accessibility**
- Web: tabs pattern (`aria-selected`, arrow keys) for view switching; native radio group for single-select; `aria-pressed` for multi-select toggles.
- iOS (VoiceOver): `UISegmentedControl` exposes selected segment and value automatically.
- Android (TalkBack): segmented buttons expose checked state; set `contentDescription` on icon-only segments.
- Each segment needs an accessible name, a visible focus indicator, and a ≥44pt / 48dp target.

**Avoid**
- Mixing selection-state and action segments in one control.
- Too many segments, or wildly unequal segment content/width.
- Using a segmented control to navigate between top-level app sections.

**Full reference:** [full reference](../../references/components/segmented-controls.md)
