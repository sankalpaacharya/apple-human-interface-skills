# Search Fields

> A search field is an editable text field, with a search icon and clear button, that lets people search content for terms they enter.

**Use it for:** Querying or filtering a collection by typed terms — inline when scoped to a view, in a header/toolbar when global.

**Implementation**

| Platform | Maps to |
| --- | --- |
| Web | `<input type="search">` in `<form role="search">` with a `<label>`; `<datalist>` or ARIA combobox for suggestions |
| SwiftUI | `.searchable(text:)` modifier (adds a search bar to `List`/`NavigationStack`); `searchSuggestions` |
| Android (Compose) | Material 3 `SearchBar` / `DockedSearchBar` |
| UIKit | `UISearchController` / `UISearchBar` |
| React Native | `TextInput` styled as search; RN Paper `Searchbar` |
| Flutter | `SearchBar` / `SearchAnchor` (Material 3); `CupertinoSearchTextField` |

**Guidelines**
- Show a search icon and a clear ("×") button so the field is recognizable and easy to reset.
- Use placeholder text to communicate scope, not as the only label.
- Search as the user types (debounced) when feasible so results refine continuously.
- Show recent searches before typing and predictive suggestions while typing.
- Order results by relevance, most-likely first; categorize when it aids scanning.
- Offer scope filters (tabs/chips/tokens); default to a broader scope and let people refine.
- On a dedicated search page, consider autofocus on arrival — but avoid it on mobile if the keyboard would cover content.

**Accessibility**
- Web: `role="search"`, accessible name via `<label>`/`aria-label`; combobox pattern for suggestions; announce result counts via `aria-live`; clear button is a real focusable control.
- iOS (VoiceOver): search bars expose Search Field trait and clear button automatically.
- Android (TalkBack): set `contentDescription` on icons; suggestion list is focus-navigable.
- Clear button and field meet ≥44pt / 48dp touch targets.

**Avoid**
- A bare text input with no clear visual search affordance.
- Suggestion lists that can't be reached or operated with the keyboard.
- Forcing the on-screen keyboard open over results on mobile.

**Full reference:** [full reference](../../references/components/search-fields.md)
