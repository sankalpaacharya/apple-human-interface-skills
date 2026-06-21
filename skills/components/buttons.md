# Buttons

> A button initiates an instantaneous action, combining style, content (text and/or icon), and a semantic role.

**Use it for:** Triggering an action (submit, save, delete, open dialog). Use a link/navigation element instead when the result is navigating to a URL or screen.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<button type="button\|submit">` (`<a>` only for navigation) |
| SwiftUI | `Button` (`.buttonStyle`, `.borderedProminent` for primary) |
| Android (Compose) | `Button` / `FilledButton`, `OutlinedButton`, `TextButton` |
| UIKit | `UIButton` |
| React Native | `Pressable` / `Button` (RN Paper `Button`) |
| Flutter | `ElevatedButton`, `OutlinedButton`, `TextButton` |

**Guidelines**
- Use one prominent/primary style per view for the most likely action; keep others lighter.
- Distinguish the preferred option with style, not size; keep buttons in a set the same size.
- Start text labels with a verb ("Add to Cart"); use familiar icons for familiar actions.
- Provide visible hover, focus, active (pressed), and disabled states.
- Style destructive actions distinctly (e.g. red); never make destructive the default that responds to Enter.
- For slow actions, show an in-button spinner and optionally swap the label.

**Accessibility**
- Web: accessible name (text/`aria-label`), Enter+Space, visible focus ring, `aria-busy` for loading.
- iOS VoiceOver: button trait + label; icon-only buttons need an accessibility label. Android TalkBack: content description.
- Touch target ≥44pt / 48dp (web aim 44×44 CSS px); don't rely on color alone for state/role.

**Avoid**
- Multiple competing prominent buttons in one view.
- Building buttons from `<div>`/`<span>` without keyboard support; removing focus outlines.
- Tiny or tightly packed tap targets.

**Full reference:** [buttons.md](../../references/components/buttons.md)
