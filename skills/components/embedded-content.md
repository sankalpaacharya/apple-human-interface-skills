# Embedded Content

> Embedded content loads and displays external rich web content (HTML, sites, media) inline within your page or app.

**Use it for:** Showing external HTML/web content inline (rendered email, a help article, a third-party widget) or briefly surfacing a website inside your app's context.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<iframe>` (`title`, `sandbox`, `loading="lazy"`, `allow`); native `<video>`/`<audio>`, `<object>`/`<embed>` |
| SwiftUI | `WebView` (iOS 26+) or `WKWebView` wrapped via `UIViewRepresentable` |
| Android (Compose) | `WebView` inside `AndroidView` |
| UIKit | `WKWebView` (use `SFSafariViewController` for general browsing) |
| React Native | `react-native-webview` `WebView` |
| Flutter | `webview_flutter` `WebViewWidget` |

**Guidelines**
- Support forward/back navigation only when people visit multiple pages, with explicit controls.
- Don't rebuild a full browser inside an embed — link out for general browsing.
- Lazy-load offscreen embeds to keep the page fast.
- Sandbox untrusted content and grant only the permissions it needs.
- Size the frame to its content and make it responsive.

**Accessibility**
- Web: give each `<iframe>` a descriptive `title`; keep embedded content keyboard-reachable with sensible focus order; don't trap focus.
- iOS VoiceOver / Android TalkBack: ensure the web view's content is exposed to the screen reader.
- Provide a meaningful fallback or label if the embed fails to load.

**Avoid**
- Replicating Safari/browser functionality inside the app.
- Untitled or unsandboxed iframes hosting untrusted content.

**Full reference:** [web-views.md](../../references/components/web-views.md)
