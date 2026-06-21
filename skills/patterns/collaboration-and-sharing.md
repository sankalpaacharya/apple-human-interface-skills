# Collaboration and Sharing

> Simple, responsive ways for people to share content and collaborate on it while communicating with others.

**Use it for:** Documents, boards, or content multiple people view or edit together, or any content users may want to share out.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Web Share API (`navigator.share`), shareable links with scopes, WebSockets + CRDT (Yjs/Automerge) for live edit/presence |
| SwiftUI | `ShareLink` / `UIActivityViewController`, CloudKit sharing (`CKShare`), universal links |
| Android (Compose) | `Intent.ACTION_SEND` chooser (`ShareSheet`), App Links, Firebase/realtime backend for presence |
| React Native | `Share.share()`, `react-native-share`, deep links via `Linking` |
| Flutter | `share_plus`, deep links via `app_links`/`uni_links` |

**Guidelines**
- Place a Share action in a consistent, convenient spot (toolbar/header).
- Invoke the OS share sheet where available; fall back to a custom menu (copy link, email, social) elsewhere.
- Offer concise permission options in plain language ("Anyone with the link can view"); keep choices minimal.
- Let people both "send a copy" and "collaborate" where relevant.
- Once collaboration starts, show a persistent indicator of who's sharing/present near the Share control.
- Notify collaborators of relevant events (mentions, edits, joins) with deep links back to the right view.

**Accessibility**
- Make share/collaboration controls real buttons with descriptive labels; keep menus keyboard-navigable and focus-managed.
- Announce presence and content changes politely (ARIA live region / VoiceOver / TalkBack).
- Don't identify collaborators by avatar color alone — include names/initials as text.

**Avoid**
- Burying the share entry point or overwhelming users with too many permission options.
- Ambiguous permission wording that hides who can see or edit content.

**Full reference:** [full reference](../../references/patterns/collaboration-and-sharing.md)
