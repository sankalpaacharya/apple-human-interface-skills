# Touch and Gestures

> Physical motions — tap, swipe, drag, pinch — that directly manipulate on-screen objects on touch devices.

**Use it for:** Touchscreen and hybrid devices — tap to activate, swipe-to-dismiss or row actions, drag-to-reorder, pinch-to-zoom; custom gestures only for specialized, frequent tasks.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | Pointer Events (`pointerdown`/`move`/`up`), CSS `touch-action` (`pan-y`, `none`); let browser own pinch-zoom/edge swipes |
| SwiftUI | `.gesture` (`TapGesture`, `DragGesture`, `MagnifyGesture`, `LongPressGesture`), `.swipeActions`, `.draggable`/`.dropDestination` |
| Android (Compose) | `Modifier.pointerInput` + `detectTapGestures`/`detectDragGestures`/`detectTransformGestures`, `swipeable`/`anchoredDraggable` |
| React Native | `Pressable`, Gesture Handler (`Gesture.Pan`/`Pinch`/`LongPress`), `ScrollView`; legacy `PanResponder` |
| Flutter | `GestureDetector` (`onTap`/`onPanUpdate`/`onScaleUpdate`/`onLongPress`), `Dismissible`, `ReorderableListView` |

**Guidelines**
- Match expectations for standard gestures: tap selects/activates, swipe scrolls or reveals, drag moves, long-press shows more options.
- Don't repurpose a familiar gesture for an app-unique action, or invent one for a standard action.
- Respond with immediate, continuous feedback so users can predict a gesture's result mid-motion.
- Make every gesture-driven action also reachable a simpler way (a visible button); gestures supplement, not replace.
- Treat custom gestures as discoverable, easy, and distinct; teach them in context, never as the only path to an important action.
- Declare which gestures you handle (e.g. `touch-action`, scroll direction) so scrolling stays smooth.
- Indicate clearly when a gesture isn't available so users don't think the UI is frozen.

**Accessibility**
- Provide non-gesture alternatives (buttons, links) for users who can't swipe/pinch; never gate functionality behind a single gesture.
- Keep tap targets at least ~44pt/dp and well-spaced.
- Don't disable system pinch-zoom (avoid `user-scalable=no`); users rely on it to read.
- Support keyboard and VoiceOver/TalkBack equivalents (custom actions) for any drag, swipe, or reorder.

**Avoid**
- Hijacking native gestures: edge-swipe back/forward, pull-to-refresh, pinch-zoom, two-finger scroll.
- Custom multi-finger or hard-to-describe gestures as the only way to do something.
- Gestures with no visible feedback or affordance hinting they exist.

**Full reference:** [full reference](../../references/inputs/gestures.md)
