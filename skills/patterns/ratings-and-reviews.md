# Ratings and Reviews

> Asking people for feedback on your product at the right moment, without nagging.

**Use it for:** Prompting for a rating/review after the user has had a genuinely positive, completed experience.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | No native prompt — custom in-app modal/banner, link out to a review platform, gate frequency via client/server state; star widget = accessible radio group |
| SwiftUI | `requestReview` (`StoreKit`/SwiftUI environment), App Store review |
| Android (Compose) | Play In-App Review API (`ReviewManager`) |
| React Native | `react-native-store-review` / `expo-store-review` (`StoreReview.requestReview`) |
| Flutter | `in_app_review` package (`requestReview`) |

**Guidelines**
- Ask only after demonstrated engagement — completing a key task, a milestone, or repeat usage — never on first visit or during onboarding.
- Time prompts to natural stopping points; don't interrupt an active task or flow.
- Don't pester: space requests well apart (weeks), cap how often you ask, only re-ask after further engagement.
- Make the prompt lightweight — one tap/click to rate or dismiss — and never block the UI behind it.
- Let users easily opt out of future prompts. A great overall experience earns ratings better than aggressive prompting.
- Note: native store-review APIs are rate-limited by the OS and may not always show.

**Accessibility**
- Build star inputs as an accessible radio group with labels like "Rate 4 of 5 stars"; make them keyboard/switch operable.
- Ensure any custom prompt is a focus-trapped, dismissible dialog with a labeled close control.
- Don't convey rating state with color/icon alone — expose the value as text to assistive tech (VoiceOver / TalkBack).

**Avoid**
- Requesting ratings on first launch, mid-task, or repeatedly.
- Modal prompts that can't be dismissed or that block progress.

**Full reference:** [full reference](../../references/patterns/ratings-and-reviews.md)
