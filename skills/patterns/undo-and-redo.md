# Undo and Redo

> Letting people reverse and re-apply recent actions so they can explore and recover from mistakes safely.

**Use it for:** Editors, drawing/design tools, form-heavy apps — anywhere a destructive or experimental action should be reversible.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | App-state command/history stack (Redux undo middleware, Zustand history); text inputs get native `Ctrl/Cmd+Z` |
| SwiftUI | `UndoManager` (environment), shake-to-undo on iOS, `.undo`/`.redo` actions |
| Android (Compose) | Custom command/history stack in state; `Snackbar` with "Undo" action for reversible ops |
| React Native | Custom state-history stack (`redux-undo`, `zundo`); `react-native` Snackbar "Undo" |
| Flutter | `UndoHistory`/`UndoController`, or custom command stack; `SnackBar` action |

**Guidelines**
- Help people predict outcomes: label undo/redo with the specific action ("Undo Typing"), not a bare arrow.
- Show the result of an undo/redo — scroll to or highlight the affected content even if it was offscreen.
- Allow multiple levels back to a logical checkpoint (open, last save); avoid arbitrary limits.
- Batch related micro-changes (repeated slider nudges) into a single undo step; offer "revert all" when useful.
- Support standard shortcuts (`Cmd/Ctrl+Z` undo, `Shift+Cmd/Ctrl+Z`/`Ctrl+Y` redo); add visible buttons where discoverability matters (touch UIs).
- For irreversible actions, prefer a brief "Undo" toast/snackbar window over an upfront confirm dialog.

**Accessibility**
- Ensure undo/redo controls are keyboard/switch operable and labeled ("Undo bold").
- Announce the result of an undo via a live region / VoiceOver / TalkBack so non-visual users know what changed.

**Avoid**
- Silent undos with no visible result (users repeat the action thinking it failed).
- Redefining standard shortcuts or capping undo depth unnecessarily.

**Full reference:** [full reference](../../references/patterns/undo-and-redo.md)
