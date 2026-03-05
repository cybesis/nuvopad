# Changelog

All notable changes to Nuvopad are documented here.

---

## [2.4.0] — 2026-03-05

### Fixed
- Template notes dragged to Quick Pins now correctly show the template icon instead of the generic note icon.
- Clicking a template Quick Pin no longer opens a blank note — the full template body is applied immediately.
- Loading screen logo now renders correctly in Microsoft Store (MSIX) builds where the Tauri custom protocol handler is not yet registered during HTML parse.
- All app data and log files now live under a single canonical path (`%APPDATA%\CybesisStudios.Nuvopad\`) — no more split between `APPDATA` and `LOCALAPPDATA`.

---

## [2.3.0] — 2026-03-01

### Added
- **Cursor memory**: Caret position is persisted per note and restored when you reopen it — no more jumping to the top.

### Improved
- Validation layer added to all Tauri IPC commands — malformed payloads now return descriptive errors instead of silent failures.
- Pro feature gates applied consistently to all new UI surfaces.

---

## [2.2.0] — 2026-02-26

### Improved
- Quick Pins sidebar section now shows the correct icon per item type: notebook folder, template layout, or note.
- Drag-and-drop correctly classifies template notes as `template` pins (not `note`) when dropped onto the Quick Pin zone.

---

## [2.1.0] — 2026-02-24

### Fixed
- Real-time sidebar preview stays in sync with editor content when switching notes rapidly.
- Various stability improvements under high note-switching frequency.

---

## [2.0.0] — 2026-02-22

### Added
- **Quick Pins**: Pin any note, template, or notebook to a persistent Quick Pin section in the sidebar for instant one-click access.
- **Drag & Drop**: Drag note cards into Inbox, Favorites, Trash, any Notebook, or the Quick Pin zone.
- **Trash drag confirmation**: A confirmation dialog guards against accidental permanent deletion when dropping notes onto Trash.

---

## [1.5.0] — 2026-02-21

### Added
- **Windows Store purchase flow**: Buy and activate the Pro upgrade directly from within the app via the native Windows Store dialog.

### Improved
- Pro license checks now use the Windows Store licensing API (`windows::Services::Store`) instead of the local stub.

---

## [1.4.0] — 2026-02-20

### Improved
- **Faster startup**: UI bundle split into focused vendor chunks (React, editor, UI components, i18n) — main bundle reduced from 1.3 MB to 357 kB.
- **Cleaner language switching**: i18n module now initializes synchronously on startup, eliminating a redundant async import that could delay language application.

### Internal
- Added `manualChunks` to Vite config for Tiptap/ProseMirror, Radix UI, React, and i18n libraries.
- Resolved Vite `[plugin:vite:reporter]` mixed static/dynamic import warning for `i18n/index.ts`.

---

## [1.3.0] — 2026-02-20

### Internal
- Version preparation and dependency updates.

---

## [1.2.1] — 2026-02-20

### Fixed
- **Instant sidebar updates**: Note title and body preview in the sidebar now update in real time as you type — no more ~2-second lag.
- **Delete shortcut UX**: After deleting a note via keyboard shortcut, the adjacent note is automatically selected and the sidebar retains focus so you can delete the next note immediately without an extra click.
- **Favorites / Trash headers**: The sidebar now shows the correct section label ("FAVORITES" or "TRASH") and contextually appropriate empty-state messages instead of always showing "NOTES / No notes yet".
- **Focus ring artifact**: Removed an unintended blue focus outline that appeared in the note list after deleting a note.

### Internal
- All Rust source files formatted with `cargo fmt`.
- Resolved three Clippy lint warnings (`redundant_closure`, `needless_return` × 2).
- Fixed a `next/image` ESLint warning in the marketing site.
- Switched Vitest worker pool to `threads` for reliable test execution on Windows.

---

## [1.2.0] — 2026-02-15

### Added
- **Favorites**: Star any note to pin it to the Favorites view for quick access.
- **Trash / Soft Delete**: Deleted notes move to Trash and can be restored or permanently removed.
- **Attachments**: Drag-and-drop image and file attachments directly into notes (Pro).
- **Export**: Export individual notes as Markdown, HTML, or plain text.

### Fixed
- Various stability improvements and performance optimizations.

---

## [1.1.2] — 2026-02-10

### Fixed
- Minor UI polish and stability fixes.

---

## [1.1.1] — 2026-02-08

### Fixed
- Hotfix for occasional crash on startup when the database schema migration ran on a fresh install.

---

## [1.0.4] — 2026-02-07

### Added
- Initial Microsoft Store release.
- Local-first SQLite storage.
- Markdown editing with WYSIWYG and Source Mode toggle.
- Notebooks, Tags, and instant search.
- Pro add-on: Focus Mode, custom templates, advanced themes, data backup.
