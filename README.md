# Apple Human Interface Skills

> Apple's [Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines) scraped in full and distilled into agent-usable, **multi-platform** design skills for **web and mobile** app development.

This is an [Agent Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills): drop it where your coding agent can read it and it will pull Apple's design guidance — mapped to real code — while building UIs.

## What's inside

| Path | Contents |
| --- | --- |
| `SKILL.md` | Entry point — skill manifest + router table the agent reads first. |
| `skills/` | **65** distilled skills across foundations, patterns, components, interaction. Each maps an Apple HIG concept to Web / SwiftUI / Android Compose / React Native / Flutter, with guidelines, accessibility, and anti-patterns. |
| `references/` | The **172** full HIG pages (converted to Markdown) for deep dives. Every skill links to its source page here. |

## Platforms covered

Each skill's **Implementation** table gives the concrete mapping for:

- **Web** — semantic HTML, ARIA roles, CSS
- **iOS / macOS** — SwiftUI (and UIKit where it differs)
- **Android** — Jetpack Compose / Material 3
- **Cross-platform** — React Native and Flutter

## Example skill

Each file looks like this (abridged):

```markdown
# Toggles
> A toggle lets people choose between a pair of opposing states (on/off).

**Implementation**
| Platform | Maps to |
| --- | --- |
| Web | `<button role="switch" aria-checked>` or `<input type="checkbox">` |
| SwiftUI | `Toggle` |
| Android (Compose) | `Switch` / `Checkbox` / `RadioButton` |
| React Native | `Switch` (core) |
| Flutter | `Switch` / `CupertinoSwitch` |

**Guidelines** · **Accessibility** · **Avoid** · **Full reference**
```

## Index

### Foundations

- **[Accessibility](skills/foundations/accessibility.md)** — Building interfaces everyone can perceive, operate, and understand regardless of ability or context.
- **[Branding](skills/foundations/branding.md)** — Expressing a recognizable brand identity while keeping the experience familiar and content-first.
- **[Color](skills/foundations/color.md)** — Use color deliberately to communicate status, express brand, convey hierarchy, and provide continuity — not as decoration.
- **[Dark Mode](skills/foundations/dark-mode.md)** — A systemwide dark color palette for low-light viewing that users expect every app and site to respect automatically.
- **[Icon Systems](skills/foundations/icon-systems.md)** — A consistent, configurable library of symbols that align with your typography across all weights and sizes.
- **[Icons (Interface Icons / Glyphs)](skills/foundations/icons.md)** — Simple graphic symbols that express a single action, item, or mode in a way people instantly understand.
- **[Images](skills/foundations/images.md)** — Delivering artwork at the right format and resolution so it looks sharp on every display.
- **[Inclusion](skills/foundations/inclusion.md)** — Putting people first by using respectful language and imagery and presenting content everyone can access and understand.
- **[Layout](skills/foundations/layout.md)** — A consistent, adaptive layout grounds people in content and works across screen sizes and orientations.
- **[Materials](skills/foundations/materials.md)** — Translucent, blurred effects that separate a floating control/navigation layer from background content, creating depth while keeping foreground elements legible.
- **[Motion](skills/foundations/motion.md)** — Purposeful, fluid animation that conveys status, gives feedback, and enriches the experience — without distracting or causing discomfort.
- **[Privacy](skills/foundations/privacy.md)** — Being transparent about the data and device capabilities you need, and protecting whatever people let you access.
- **[Right to Left (RTL)](skills/foundations/right-to-left.md)** — Mirroring your interface to match the reading direction of RTL scripts like Arabic and Hebrew.
- **[Typography](skills/foundations/typography.md)** — Typographic choices establish legibility, hierarchy, and brand through deliberate use of size, weight, and a limited set of typefaces.
- **[Writing](skills/foundations/writing.md)** — The words in your interface — labels, messages, empty states, errors — are a core part of the user experience.

### Patterns

- **[Collaboration and Sharing](skills/patterns/collaboration-and-sharing.md)** — Simple, responsive ways for people to share content and collaborate on it while communicating with others.
- **[Drag and Drop](skills/patterns/drag-and-drop.md)** — Moving or copying content by dragging a selection from a source location to a destination.
- **[Entering Data](skills/patterns/entering-data.md)** — Designing form input so people can supply information quickly and without mistakes.
- **[Feedback](skills/patterns/feedback.md)** — Cues that tell people what's happening, the result of an action, and how to avoid mistakes.
- **[File Management](skills/patterns/file-management.md)** — Letting people create, open, save, browse, and preview documents and files within an app.
- **[Launching](skills/patterns/launching.md)** — The startup experience from open to first interactive screen — ideally instant.
- **[Loading](skills/patterns/loading.md)** — Handling waits for content so they don't disrupt the experience — ideally finishing before people notice.
- **[Managing Accounts](skills/patterns/managing-accounts.md)** — Authentication and account flows that let people access their content without becoming a barrier to entry.
- **[Modality](skills/patterns/modality.md)** — Content shown in a dedicated mode that blocks interaction with the rest of the app until explicitly dismissed.
- **[Notifications](skills/patterns/notifications.md)** — Timely, permission-gated messages that inform people of events, delivered respectfully without over-interrupting.
- **[Offering help](skills/patterns/offering-help.md)** — Contextual help — tips, tooltips, and links — offered when an interface isn't fully self-explanatory.
- **[Onboarding](skills/patterns/onboarding.md)** — A fast, optional flow that helps people get a quick start using your app.
- **[Ratings and Reviews](skills/patterns/ratings-and-reviews.md)** — Asking people for feedback on your product at the right moment, without nagging.
- **[Search](skills/patterns/search.md)** — Lets people find content within your app, optionally scoped or filtered.
- **[Settings](skills/patterns/settings.md)** — A place for general, infrequently changed preferences that customize the experience.
- **[Undo and Redo](skills/patterns/undo-and-redo.md)** — Letting people reverse and re-apply recent actions so they can explore and recover from mistakes safely.

### Components

- **[Action Sheets](skills/components/action-sheets.md)** — An action sheet presents a set of choices related to an action the user just initiated, typically from the screen edge.
- **[Alerts](skills/components/alerts.md)** — An alert is a modal dialog that delivers critical information and requires the user to respond before continuing.
- **[Boxes](skills/components/boxes.md)** — A box visually groups logically related content and controls, set off by a border or background.
- **[Buttons](skills/components/buttons.md)** — A button initiates an instantaneous action, combining style, content (text and/or icon), and a semantic role.
- **[Charts](skills/components/charts.md)** — A chart organizes data visually to highlight key insights and help people understand and decide.
- **[Color Pickers](skills/components/color-pickers.md)** — A color picker (Apple "color well") lets people choose and adjust a color for text, shapes, or other elements.
- **[Combo Boxes](skills/components/combo-boxes.md)** — A combo box combines a text field with a dropdown list, so people can type a custom value or pick from predefined options.
- **[Context Menus](skills/components/context-menus.md)** — A context menu provides quick access to actions relevant to a specific item or view, revealed on demand (right-click / long-press).
- **[Disclosure Controls (Expand/Collapse)](skills/components/disclosure-controls.md)** — Controls that reveal or hide related information or functionality, keeping advanced or secondary content out of the way until it's needed.
- **[Embedded Content](skills/components/embedded-content.md)** — Embedded content loads and displays external rich web content (HTML, sites, media) inline within your page or app.
- **[Labels](skills/components/labels.md)** — A label is static, uneditable text that people can read (and often copy) but not edit.
- **[Lists and Tables](skills/components/lists-and-tables.md)** — Lists and tables present data in rows (and optionally columns), supporting scanning, selection, navigation, and editing.
- **[Menus](skills/components/menus.md)** — A menu reveals a list of commands, options, or states when the user activates a trigger, presenting actions in a space-efficient popup.
- **[Pickers](skills/components/pickers.md)** — A picker presents one or more scrollable lists of distinct values to choose from, including date and time pickers.
- **[Popovers](skills/components/popovers.md)** — A popover is a transient view anchored to a control that appears above other content when clicked or tapped.
- **[Progress Indicators](skills/components/progress-indicators.md)** — Progress indicators show that an app is working during loading or a lengthy operation, optionally estimating time remaining.
- **[Scrolling (Scroll Views & Sticky Headers)](skills/components/scrolling.md)** — A scrollable region lets people view content larger than its container by moving it vertically or horizontally, with indicators that show position.
- **[Search Fields](skills/components/search-fields.md)** — A search field is an editable text field, with a search icon and clear button, that lets people search content for terms they enter.
- **[Segmented Controls](skills/components/segmented-controls.md)** — A segmented control is a linear set of two or more equal-width segments, each acting as a button, offering a single choice from a related set.
- **[Select Menus](skills/components/select-menus.md)** — A select menu (Apple "pop-up button") displays a menu of mutually exclusive options and updates to show the current selection.
- **[Sheets](skills/components/sheets.md)** — A sheet presents a focused, self-contained task closely related to the current context, layered over the page.
- **[Sidebars (Side Navigation / Drawer)](skills/components/sidebars.md)** — A panel on the leading (left) side of a view for navigating between app areas or top-level content collections like folders and playlists.
- **[Sliders](skills/components/sliders.md)** — A slider is a track with a draggable thumb that people adjust between a minimum and maximum value.
- **[Split Views (Master–Detail / Multi-Pane Layout)](skills/components/split-views.md)** — A layout of two or three adjacent panes where selecting an item in one pane updates the contents of the next (e.g. list → detail).
- **[Steppers](skills/components/steppers.md)** — A stepper is a two-segment control (increment/decrement) for changing a value by a fixed amount.
- **[Tab Bars (Primary / Bottom Navigation)](skills/components/tab-bars.md)** — A persistent bar of top-level destinations that lets people switch between the main sections of an app while preserving each section's state.
- **[Text Fields](skills/components/text-fields.md)** — A text field is a rectangular area where people enter or edit a small, specific piece of text such as a name or email.
- **[Toggles](skills/components/toggles.md)** — A toggle lets people choose between a pair of opposing states (on/off), using a distinct appearance for each state.
- **[Toolbars](skills/components/toolbars.md)** — A horizontal bar of frequently used commands, controls, navigation, and search along the top (or bottom) edge of a view, acting on the current content.
- **[Windows](skills/components/windows.md)** — A window is the bounded surface that presents an app's content; on the web it maps to the browser viewport, and on mobile to the device screen / scene.

### Interaction

- **[Focus and Selection](skills/interaction/focus-and-selection.md)** — Focus visually marks the element an interaction targets; selection marks the item(s) a user has chosen to act on.
- **[Keyboard](skills/interaction/keyboard.md)** — Physical-keyboard input for text entry, shortcuts, and navigating an interface without a pointer.
- **[Pointer and Hover](skills/interaction/pointer-and-hover.md)** — Mouse and trackpad input for precise navigation, hover feedback, and contextual (right-click) actions.
- **[Touch and Gestures](skills/interaction/touch-and-gestures.md)** — Physical motions — tap, swipe, drag, pinch — that directly manipulate on-screen objects on touch devices.

## Provenance

Source: Apple Human Interface Guidelines (developer.apple.com), scraped 2026-06-21 via the site's Swift-DocC JSON API, converted to Markdown, then distilled for multi-platform use. All design guidance © Apple; this repository is an unofficial, educational reference.
