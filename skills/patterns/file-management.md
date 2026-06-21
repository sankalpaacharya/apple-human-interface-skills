# File Management

> Letting people create, open, save, browse, and preview documents and files within an app.

**Use it for:** Apps that let users open, edit, save, or attach documents/files (editors, uploaders, document viewers).

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<input type="file">`, File System Access API, drag-drop upload, blob downloads (`<a download>`), inline preview (PDF.js/`<embed>`/media) |
| SwiftUI | `.fileImporter`/`.fileExporter`, `DocumentGroup`, `QuickLook`, autosave via document model |
| Android (Compose) | Storage Access Framework (`ActivityResultContracts.OpenDocument`/`CreateDocument`), `DocumentFile`, `FileProvider` |
| React Native | `react-native-document-picker`, `expo-document-picker`/`expo-file-system`, `react-native-fs` |
| Flutter | `file_picker`, `path_provider`, `open_filex` / `printing` for preview |

**Guidelines**
- Give convenient ways to create/open files: a visible New/Add (+) button plus familiar shortcuts.
- If you build a custom file browser, mirror users' mental model — open at the most relevant location but let them navigate.
- Autosave continuously instead of forcing explicit Save; persist on edit, on close, and when switching away.
- When autosave is off, clearly signal unsaved changes (dirty indicator, "Edited") and prompt to save before leaving.
- Hide file extensions by default but let users see them; reflect the choice consistently.
- Let users choose destination and format when saving/exporting; default filename and location sensibly.
- Provide previews so people can view a file without fully opening it, even for types your app can't edit.

**Accessibility**
- Ensure pickers and custom browsers are keyboard-navigable with labeled controls.
- Announce save status changes (saved / unsaved / saving) via live region / VoiceOver / TalkBack.
- Provide accessible text alternatives for file thumbnails and preview controls.

**Avoid**
- Forcing manual saves with no safety net against lost work.
- Showing a "dirty" indicator while autosave is active (implies action is needed).

**Full reference:** [full reference](../../references/patterns/file-management.md)
