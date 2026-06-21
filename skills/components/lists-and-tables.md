# Lists and Tables

> Lists and tables present data in rows (and optionally columns), supporting scanning, selection, navigation, and editing.

**Use it for:** Rows of mostly textual data people scan and read. Use a real table for multi-column sortable data; a list for single-column hierarchies or navigation.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<table>` (`<thead>`/`<th scope>`); `<ul>`/`<ol>` or `role="listbox"`; `role="tree"` for outlines |
| SwiftUI | `List`, `Table` (multi-column), `OutlineGroup` for trees |
| Android (Compose) | `LazyColumn` / `LazyRow`; `LazyVerticalGrid` for grids |
| UIKit | `UITableView` (lists), `UICollectionView` (grids/compositional) |
| React Native | `FlatList` / `SectionList` (table libs for columns) |
| Flutter | `ListView` / `ListView.builder`; `DataTable` for columns |

**Guidelines**
- Prefer lists/tables for text-heavy content; use a grid/collection for image-heavy or size-varying items.
- Keep row text succinct to minimize truncation; reveal long details in a separate view.
- Use descriptive column headings (nouns, Title Case, no trailing punctuation).
- Provide clear selection feedback; allow editing (reorder, add, delete) when it makes sense.
- Use a chevron/disclosure for drill-in; an info button only to reveal more info.
- Tables: click header to sort (toggle on repeat), allow column resizing, use alternating row colors when wide.
- Use an outline/tree for hierarchical data rather than a flat table.

**Accessibility**
- Web: semantic `<table>` with `<th scope>` and `aria-sort`; selectable lists use `role="listbox"`/`option` + `aria-selected`; trees use `role="tree"`/`treeitem` + `aria-expanded`/`aria-level`.
- iOS VoiceOver / Android TalkBack: rows expose labels, selection state, and traits/actions; support swipe actions accessibly.
- Don't rely on color alone for selection — pair with a checkmark/icon; touch targets ≥44pt / 48dp.

**Avoid**
- Using table markup for layout, or `<div>` soup where a table belongs.
- Over-tall rows packed with large text blocks.
- Mixing a trailing alphabetical index with trailing row controls.

**Full reference:** [lists-and-tables.md](../../references/components/lists-and-tables.md)
