# Drag and Drop

> Moving or copying content by dragging a selection from a source location to a destination.

**Use it for:** Reordering lists/boards, moving items between containers, uploading files, or transferring content between views/apps.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | HTML Drag and Drop API (`draggable`, `DataTransfer`) for files; pointer events via dnd-kit/react-dnd/SortableJS for in-app reorder |
| SwiftUI | `.draggable`/`.dropDestination`, `.onDrag`/`.onDrop`, `onMove` for list reorder |
| Android (Compose) | `dragAndDropSource`/`dragAndDropTarget` modifiers; `detectDragGestures` / Reorderable lists |
| React Native | `react-native-gesture-handler` + `reanimated`, `react-native-draggable-flatlist` |
| Flutter | `Draggable`/`DragTarget`, `ReorderableListView` |

**Guidelines**
- Support drag where expected, but always offer a non-drag alternative (menu/button) — drag is hard for some users.
- Decide move vs. copy by context (within container = move, across = copy); honor the expected convention to avoid data loss.
- Support multi-item drag where it makes sense; let people undo a drop or confirm an irreversible one.
- Offer multiple data representations highest-to-lowest fidelity so the destination picks the richest it supports.
- Show a translucent drag preview; indicate valid vs. invalid drop targets and clear feedback when the item leaves.
- On invalid drop, animate the item back to its source; auto-scroll near container edges; show progress for slow transfers.

**Accessibility**
- Provide a keyboard-operable alternative (cut/paste, move buttons, arrow-key reorder) — native HTML5 drag isn't keyboard accessible.
- Announce drag start, valid targets, and drop results (ARIA live / VoiceOver / TalkBack); dnd-kit and platform reorder APIs ship a11y announcements.

**Avoid**
- Making drag the only way to perform an action.
- Unexpected move/copy behavior or no feedback on hover/invalid drop.

**Full reference:** [full reference](../../references/patterns/drag-and-drop.md)
