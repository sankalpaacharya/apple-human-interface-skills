# Search

> Lets people find content within your app, optionally scoped or filtered.

**Use it for:** Apps with enough content that browsing alone is slow, or where people need to filter/narrow a list by attributes.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<input type="search">`/`role="searchbox"`, ARIA combobox autocomplete, filter chips; Algolia/Typesense, Downshift |
| SwiftUI | `.searchable` modifier, `.searchScopes`, `.searchSuggestions` |
| Android (Compose) | `SearchBar`/`DockedSearchBar`, filter `Chip`s, suggestion list |
| React Native | `<TextInput>` search header, `@react-navigation` search bar option, `FlatList` filtering |
| Flutter | `SearchBar`/`SearchAnchor`, `showSearch` + `SearchDelegate`, `FilterChip` |

**Guidelines**
- If search is important, give it a primary, persistent position (header, toolbar, or dedicated route).
- Provide one clearly identified global search location; add scoped/local search per section only when distinct.
- Make the current scope obvious via placeholder text, scope chips/tokens, or a heading.
- Offer recent searches before typing and suggestions/completions/corrections while typing.
- Let people refine with filters (date, type, size) shown near the results.
- Update results responsively; debounce input to avoid excessive requests.

**Accessibility**
- Use a proper search field with a visible or accessible label (`aria-label` / VoiceOver / TalkBack).
- For autocomplete, follow the combobox pattern and announce result counts via a live region.
- Make suggestions keyboard/switch navigable (arrow keys, select, dismiss).

**Avoid**
- Hiding search behind an unmarked icon when search is central.
- Exposing search history where others may see it without a way to clear it.
- Scattering content across multiple inconsistent search entry points.

**Full reference:** [full reference](../../references/patterns/searching.md)
