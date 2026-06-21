# Boxes

> A box visually groups logically related content and controls, set off by a border or background.

**Use it for:** Separating a group of related fields, settings, or info from the rest of the screen — card-style grouping in settings panes, dashboards, and forms.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<fieldset>`/`<legend>` for form groups, or `<section>` card; `role="group"` + `aria-labelledby` for generic containers |
| SwiftUI | `GroupBox`, `Section`, or `Form` sections |
| Android (Compose) | `Card` / `Surface`, or grouped `Column` with label |
| UIKit | `UIStackView` in a bordered container; grouped `UITableView` sections |
| React Native | `View` card (RN Paper `Card`) |
| Flutter | `Card` / `Container` with border, `DecoratedBox` |

**Guidelines**
- Keep a box relatively small vs. its container; near full-size stops reading as a distinct group.
- Use padding and alignment to imply subgroups instead of nesting boxes.
- Add a short title only when it clarifies the relationship; sentence-style caps, no ending punctuation.
- Place the title above the box content.

**Accessibility**
- Web: name the group via `<legend>`, heading + `aria-labelledby`, or `aria-label`; prefer `<fieldset>` for related inputs.
- iOS VoiceOver / Android TalkBack: expose a group/container label so the grouping is announced.

**Avoid**
- Nesting boxes within boxes to define subgroups.
- Boxes so large they crowd content or lose their grouping effect.

**Full reference:** [boxes.md](../../references/components/boxes.md)
