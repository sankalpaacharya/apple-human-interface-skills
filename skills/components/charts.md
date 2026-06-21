# Charts

> A chart organizes data visually to highlight key insights and help people understand and decide.

**Use it for:** Comparing values, showing change over time, or revealing trends, relationships, and outliers (bars for categories, lines for time, points for relationships).

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<svg>`/`<canvas>` (D3, Chart.js) in `role="img"` + `aria-label`, with table/text fallback |
| SwiftUI | Swift Charts (`Chart` with `BarMark`, `LineMark`, `PointMark`) |
| Android (Compose) | Vico, MPAndroidChart, or `Canvas`-drawn charts |
| UIKit | `UIView` + Core Graphics, or a charting library |
| React Native | Victory Native, `react-native-svg`-based libs |
| Flutter | `fl_chart`, `charts_flutter`, or `CustomPaint` |

**Guidelines**
- Choose the mark type from the message; combine types (line + points) when it clarifies.
- Use a fixed axis range when min/max are meaningful (0–100%); dynamic range when values vary widely.
- Choose the lower bound deliberately — zero suits bar comparisons but can hide differences far from zero.
- Use familiar tick sequences and only as many grid lines as needed.
- Keep data the most prominent layer; give an informative title summarizing the main message.
- Let people scrub/hover for values, but never require interaction to reveal critical info.

**Accessibility**
- Provide a text summary of type, axes, bounds, and main takeaway; add labels per mark/group.
- Don't rely on color alone — use shape, pattern, or direct labels; add separators between adjacent colors.
- Web: keyboard + AT navigation in logical (axis) order. iOS/Android: expose data via VoiceOver/TalkBack, audio graphs where available.
- Announce important changes for AT/reduced-motion users, not via animation alone.

**Avoid**
- Conveying essential information through color alone.
- Cluttering with excessive grid lines or labels.
- Hiding key information behind required interactions.

**Full reference:** [charts.md](../../references/components/charts.md)
