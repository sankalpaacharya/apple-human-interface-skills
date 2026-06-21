# Loading

> Handling waits for content so they don't disrupt the experience — ideally finishing before people notice.

**Use it for:** Content or assets that take more than a moment to fetch or render, especially when you can show useful structure or partial data while the rest loads.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Skeleton screens, spinners, `<progress>`/`role="progressbar"`, lazy-load, optimistic UI, React Suspense |
| SwiftUI | `ProgressView` (indeterminate/determinate), `.redacted(reason: .placeholder)` skeletons, `.task` async loads |
| Android (Compose) | `CircularProgressIndicator`/`LinearProgressIndicator`, shimmer/placeholder modifiers, `LaunchedEffect` loads |
| React Native | `ActivityIndicator`, `<Progress>` libs, skeleton libs (`react-content-loader`) |
| Flutter | `CircularProgressIndicator`/`LinearProgressIndicator`, `shimmer` package, `FutureBuilder` |

**Guidelines**
- Show something immediately (skeletons, placeholders) so a blank screen isn't read as broken.
- Replace placeholders progressively as real content arrives.
- Let people interact with other parts of the app while content loads in the background.
- Use a determinate progress bar when duration is known; an indeterminate spinner when it isn't.
- For unavoidably long waits, show something useful (tips, partial content) and estimate remaining time.
- Prefer a brief loading indicator over a blank screen for short (1–2s) waits.

**Accessibility**
- Expose determinate progress with value/min/max to assistive tech (`role="progressbar"` / platform progress semantics).
- Announce loading start/finish via live region / `aria-busy` / VoiceOver / TalkBack.
- Respect reduced-motion preferences for spinner/skeleton animations.

**Avoid**
- Blank screens with no indication anything is happening.
- Blocking the whole UI when partial interaction is possible.
- Indeterminate spinners when you actually know the progress.

**Full reference:** [full reference](../../references/patterns/loading.md)
