# Offering help

> Contextual help — tips, tooltips, and links — offered when an interface isn't fully self-explanatory.

**Use it for:** A new or non-obvious feature, a control whose purpose needs a brief explanation, or a complex task warranting a short tutorial or docs link.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Tooltips (`aria-describedby` popover), inline hint/coachmark components, help links; tour libs (Driver.js, Shepherd.js) |
| SwiftUI | `.help()` tooltip, `TipKit` for contextual tips, `.popover`, links via `Link` |
| Android (Compose) | `PlainTooltip`/`RichTooltip` (`TooltipBox`), inline supporting text, custom coachmark overlays |
| React Native | Tooltip libs (`react-native-walkthrough-tooltip`), coachmark/tour libs (`rn-tourguide`) |
| Flutter | `Tooltip` widget, `showcaseview` for guided tips |

**Guidelines**
- Match help to the task: inline blurb for simple actions, tutorial for multistep goals.
- Relate help to what the person is doing right now and make it easy to dismiss or ignore.
- Use tips for simple features (rule of thumb: three actions or fewer); keep them short and action-oriented.
- Use platform-appropriate wording ("tap" on mobile, "click"/"select" on web); no promotional content.
- Gate tips by eligibility (don't show to people who already use the feature) and cap frequency.
- Don't explain standard components; describe what they do specifically in your app. Add a link to relevant settings/resources.

**Accessibility**
- Make tooltip content reachable on focus, not hover only; associate it with its control.
- Ensure tips/coachmarks are keyboard/switch dismissible and announced to screen readers (VoiceOver / TalkBack).
- Don't convey help solely through an icon; pair with accessible text.

**Avoid**
- Bloated help that re-teaches standard UI or input behavior.
- Hover-only tooltips that keyboard and touch users can't trigger.
- Promotional or off-topic content inside a tip.

**Full reference:** [full reference](../../references/patterns/offering-help.md)
