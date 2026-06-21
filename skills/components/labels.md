# Labels

> A label is static, uneditable text that people can read (and often copy) but not edit.

**Use it for:** Displaying a small amount of read-only text — button captions, list-item descriptions, helper/context text. For editable text use an input; for large bodies use a text view.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<span>`/`<p>`/heading; `<label for>` to associate with a form control |
| SwiftUI | `Text` (and `Label` for text + icon) |
| Android (Compose) | `Text` |
| UIKit | `UILabel` |
| React Native | `Text` |
| Flutter | `Text` |

**Guidelines**
- Prefer system/default fonts; if you restyle, keep text legible and support user font scaling.
- Use a tiered color hierarchy: primary, secondary, tertiary (disabled), quaternary (watermark).
- Make useful text selectable so people can copy it (errors, IPs, locations).
- Respect Dynamic Type / user font-size preferences (use relative units like `rem`).

**Accessibility**
- Web: associate form labels via `<label for>` (or `aria-label`/`aria-labelledby`); use `aria-live` for live-updating text.
- iOS VoiceOver / Android TalkBack: text is read automatically; ensure decorative-only text isn't announced and meaningful text is.
- Don't convey meaning by color alone; ensure sufficient contrast for every tier.

**Avoid**
- Locking down selection on informational text users may want to copy.
- Low-contrast secondary/tertiary text that fails contrast requirements.

**Full reference:** [labels.md](../../references/components/labels.md)
