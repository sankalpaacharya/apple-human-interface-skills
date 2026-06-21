# Keyboard

> Physical-keyboard input for text entry, shortcuts, and navigating an interface without a pointer.

**Use it for:** Full keyboard operability of any interface, plus shortcuts for frequent power-user actions (search, save, new, undo) and apps with heavy text entry, grids, or lists.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `keydown`/`keyup` (`event.key`, `metaKey`/`ctrlKey`), `tabindex` + roving tabindex, arrow-key handlers |
| SwiftUI | `.keyboardShortcut(_:modifiers:)`, `.onKeyPress`, `.focusable`, `Commands` / menu builders |
| Android (Compose) | `Modifier.onKeyEvent` / `onPreviewKeyEvent`, `KeyEventType`, `Modifier.focusable` |
| React Native | `onKeyPress` (TextInput), `Pressable` `onPress`, macOS/Windows `validKeysDown`/keyboard shortcut APIs |
| Flutter | `Shortcuts`/`Actions`, `CallbackShortcuts`, `Focus` + `KeyEvent`, `Intent` bindings |

**Guidelines**
- Make every interactive element reachable and activatable by keyboard alone (Tab to move, Enter/Space to activate).
- Keep Tab order logical, following visual reading order; don't force it with positive tab indices.
- Respect standard shortcuts users know (copy/paste/cut/undo, find, save, Esc to cancel/close); don't repurpose them.
- Map custom shortcuts to the platform modifier (Cmd on macOS, Ctrl on Windows/Linux/Android).
- Define custom shortcuts only for your most frequent actions; too many makes the app hard to learn.
- Use arrow keys for moving within a composite widget (menu, list, grid, tabs), not between separate controls.
- Let Esc close modals, menus, and popovers and return focus to the trigger.
- Surface shortcuts in the UI (menu labels, tooltips, help) so they're discoverable.

**Accessibility**
- Visible focus indicator at every step (web/desktop: `:focus-visible`; never remove without replacement).
- Prevent keyboard traps — focus must be able to leave every component; manage focus into and out of modals.
- Ensure shortcuts and navigation work with VoiceOver/TalkBack and external keyboards on mobile.
- Use semantic/native controls so they're focusable and operable for free; add roles only for custom widgets.

**Avoid**
- Mouse/touch-only controls with no keyboard path.
- Overriding or shadowing standard/OS shortcuts with conflicting behavior.
- Positive tab indices that fight natural order.
- So many custom shortcuts that the app becomes hard to learn.

**Full reference:** [full reference](../../references/inputs/keyboards.md)
