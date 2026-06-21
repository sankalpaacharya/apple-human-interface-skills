# Icon Systems

> A consistent, configurable library of symbols that align with your typography across all weights and sizes.

**Use it for:** Any app needing a coherent set of interface icons across toolbars, buttons, menus, and inline with text.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | One system — SVG components/sprite or Lucide/Heroicons/Phosphor; `currentColor`, size in `em` |
| SwiftUI | SF Symbols (`Image(systemName:)`) — weights/scales align with `Font`; `.imageScale`, `.fontWeight` |
| Android (Compose) | Material Symbols / `Icons` set; consistent `Icon` sizing, `tint`, single icon family |
| React Native | A single vector-icon set (`react-native-vector-icons`) or shared SVG library, sized via props |
| Flutter | Material `Icons` (or one icon package); `IconTheme` for size/color consistency |

**Guidelines**
- Standardize on one icon system so weight, stroke, and metrics stay consistent.
- Match icon size and weight to adjacent text — size relatively and inherit text color.
- Prefer inline SVG / native symbol sets over icon fonts (better semantics and a11y).
- Use color purposefully — monochrome by default; multi-tone/accent only to add meaning.
- Use variant/state pairs (outline vs. fill, with/without slash) for selection or unavailability.
- Choose icons with RTL variants or supply flipped versions for directional glyphs.
- Animate sparingly and only for feedback/status; respect reduced-motion.
- For custom icons, match the library's optical weight, detail, and alignment.

**Accessibility**
- Give interactive icons accessible names; mark decorative ones hidden.
- For meaningful standalone icons, expose an image role with a label/title.
- Ensure 3:1 contrast against the background.
- Gate icon animations behind reduced-motion settings.

**Avoid**
- Mixing multiple icon libraries (inconsistent stroke/metrics).
- Icon fonts for new projects when SVG/native symbols are an option.
- Decorative icons announced by screen readers, or interactive icons with no label.

**Full reference:** [Apple HIG](../../references/foundations/sf-symbols.md)
