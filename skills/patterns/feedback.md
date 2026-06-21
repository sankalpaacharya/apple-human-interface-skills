# Feedback

> Cues that tell people what's happening, the result of an action, and how to avoid mistakes.

**Use it for:** Communicating ongoing status, confirming success or failure of an important action, warning before irreversible actions, or offering a way to correct a problem.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Toasts/snackbars, inline status text, `aria-live` (`role="status"`/`role="alert"`), confirm dialogs for destructive actions |
| SwiftUI | Inline status views, `.alert`/`.confirmationDialog`, `ContentUnavailableView`, haptics via `.sensoryFeedback` |
| Android (Compose) | `Snackbar` (via `SnackbarHost`), `AlertDialog`, inline supporting text, haptic feedback |
| React Native | `react-native-toast-message`/community snackbar, `Alert.alert`, `AccessibilityInfo.announceForAccessibility` |
| Flutter | `SnackBar` (`ScaffoldMessenger`), `showDialog`/`AlertDialog`, `SemanticsService.announce` |

**Guidelines**
- Match delivery to significance: passive/inline for status, interrupting dialog for critical warnings.
- Provide feedback through multiple channels (text + color + icon, not color alone).
- Integrate status near the items it describes so people see it in context.
- Reserve alerts/modals for critical, ideally actionable info; overuse dilutes them.
- Warn before unexpected, irreversible data loss — but not for expected outcomes (e.g. deleting from trash).
- Confirm completion only for significant actions; when a command can't run, say so and offer a path to resolve.

**Accessibility**
- Announce dynamic feedback via ARIA live regions / VoiceOver / TalkBack (polite for status, assertive for urgent).
- Never rely on color alone; pair with text and/or icons.
- Tie error messages programmatically to their field.

**Avoid**
- Interrupting with a modal for low-importance status.
- Color-only success/error states.
- Silent failures or generic errors with no cause or next step.

**Full reference:** [full reference](../../references/patterns/feedback.md)
