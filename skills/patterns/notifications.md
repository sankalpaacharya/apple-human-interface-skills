# Notifications

> Timely, permission-gated messages that inform people of events, delivered respectfully without over-interrupting.

**Use it for:** Delivering relevant, time-appropriate updates (messages, status changes, security alerts) or transient in-app feedback.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Web Push API + Service Worker + Notifications API (`Notification.requestPermission()`); in-app toasts for transient feedback |
| SwiftUI | `UserNotifications` (`UNUserNotificationCenter`), APNs for remote push, `requestAuthorization` |
| Android (Compose) | `NotificationCompat` + channels, FCM for push, `POST_NOTIFICATIONS` runtime permission |
| React Native | `notifee` + `@react-native-firebase/messaging`, or `expo-notifications` |
| Flutter | `flutter_local_notifications` + `firebase_messaging` |

**Guidelines**
- Request permission before sending push; ask in context (after the user shows intent), not on first load.
- Match urgency to content — reserve interrupting/high-priority delivery for genuinely time-sensitive events.
- Represent urgency honestly; misusing high priority for low-value info makes users disable notifications.
- Never use high-urgency channels for marketing; get explicit, separate opt-in for promotional notifications with easy opt-out.
- Provide an in-app settings screen to change or disable notification preferences.
- For transient in-app feedback prefer non-blocking toasts that auto-dismiss; don't require a system notification for everything.

**Accessibility**
- Announce in-app toasts to screen readers (ARIA live region / VoiceOver / TalkBack), polite vs. assertive by urgency.
- Don't auto-dismiss critical messages too fast; keep any action keyboard-reachable.
- Convey notification meaning with text/icons, not color alone.

**Avoid**
- Prompting for push permission on load before showing value.
- Marketing via notifications without consent, or inflating urgency to break through.

**Full reference:** [full reference](../../references/patterns/managing-notifications.md)
