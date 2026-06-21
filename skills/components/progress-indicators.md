# Progress Indicators

> Progress indicators show that an app is working during loading or a lengthy operation, optionally estimating time remaining.

**Use it for:** Determinate bars/rings for known-duration tasks (upload, conversion); indeterminate spinners for unquantifiable work (loading, syncing); pull-to-refresh.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<progress value max>` (determinate); `<progress>` no value or spinner with `role="status"`/`aria-live="polite"` (indeterminate) |
| SwiftUI | `ProgressView()` (spinner) / `ProgressView(value:total:)` (bar); `.refreshable` for pull-to-refresh |
| Android (Compose) | `LinearProgressIndicator` / `CircularProgressIndicator` (pass `progress` for determinate) |
| UIKit | `UIProgressView` (bar), `UIActivityIndicatorView` (spinner), `UIRefreshControl` |
| React Native | `ActivityIndicator`; RN Paper `ProgressBar`; `RefreshControl` |
| Flutter | `LinearProgressIndicator` / `CircularProgressIndicator` (`value:` for determinate); `RefreshIndicator` |

**Guidelines**
- Prefer a determinate indicator whenever progress can be measured; report it accurately and evenly (no jumping to 90% then stalling).
- Keep it animating so it doesn't look frozen; on a stall, explain the problem.
- Switch indeterminate → determinate once duration is known; don't change the indicator's shape mid-task.
- Spinner for small/constrained spaces and background tasks; bar for prominent, measurable progress; keep it in a consistent location.
- Add a short, specific description only if it helps; avoid vague "Loading…".
- Offer Cancel (and Pause where losing progress matters); confirm before canceling if progress would be lost. Don't make pull-to-refresh the only update path.

**Accessibility**
- Web: native `<progress>` exposes value; wrap status/spinner in `aria-live="polite"`; label a bare spinner; set `aria-busy` on the loading region.
- iOS (VoiceOver): set `accessibilityValue` / use `.progressViewStyle`; announce updates.
- Android (TalkBack): set `progress`/`contentDescription`; live announcements for status.
- Spinners and controls meet ≥44pt / 48dp touch targets where interactive.

**Avoid**
- Stationary indicators that imply a stalled app.
- Labeling a simple spinner when it's already obvious a process started.

**Full reference:** [full reference](../../references/components/progress-indicators.md)
