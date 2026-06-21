# Scrolling (Scroll Views & Sticky Headers)

> A scrollable region lets people view content larger than its container by moving it vertically or horizontally, with indicators that show position.

**Use it for:** Any content area that can exceed the viewport (default for most pages and panels), plus paged/snap experiences like carousels and full-screen slides.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `overflow: auto/scroll` container; `position: sticky` headers; `scroll-snap-type`/`scroll-snap-align`; `overscroll-behavior` |
| SwiftUI | `ScrollView`, `List`, `LazyVStack`; `.scrollTargetBehavior(.paging)`; pinned section headers |
| Android (Compose) | `LazyColumn` / `LazyRow` / `Modifier.verticalScroll`; `stickyHeader`; snap via `rememberSnapFlingBehavior` |
| UIKit | `UIScrollView`, `UICollectionView` (paging via `isPagingEnabled`) |
| React Native | `ScrollView`, `FlatList` (`pagingEnabled`, `snapToInterval`), `SectionList` (sticky headers) |
| Flutter | `SingleChildScrollView`, `ListView`, `CustomScrollView` with `SliverPersistentHeader`/`PageView` |

**Guidelines**
- Support native scrolling gestures, wheel, and keyboard; don't break momentum/elastic behavior.
- Make scrollability apparent — let content peek at the edge so people see there's more.
- Don't nest two scroll areas with the same orientation; a horizontal scroller inside a vertical one is fine.
- For paging use snap; keep a small overlap of context and show a page indicator when in page mode.
- Auto-scroll only when it helps (bring search results, insertion point, or selection into view), scrolling the minimum needed.
- Sticky toolbars/headers: give subtle separation (shadow, blur, solid background) so pinned controls stay legible; one effect per scroll region.
- In multi-pane layouts each pane scrolls independently; keep pinned-header heights aligned.

**Accessibility**
- Web: focusable children make a region keyboard-reachable; else give it `tabindex="0"` + accessible name; expose page via `aria-current`.
- iOS (VoiceOver) / Android (TalkBack): scroll actions are handled by native scroll views; expose current page/position.
- Respect reduced-motion (`prefers-reduced-motion` / `UIAccessibility.isReduceMotionEnabled` / `Settings.Global.ANIMATOR_DURATION_SCALE`) for smooth/parallax scrolling.

**Avoid**
- Hijacking native scroll with custom code that breaks momentum, keyboard, or accessibility.
- Nested same-axis scroll regions.
- Scroll-jacking parallax that interferes with reading or reduced-motion users.

**Full reference:** [full reference](../../references/components/scroll-views.md)
