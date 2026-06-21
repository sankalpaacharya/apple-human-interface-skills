---
name: apple-human-interface-skills
description: Apple Human Interface Guidelines distilled into agent-usable design skills for building web and mobile UIs. Use when designing, building, or reviewing any user interface: choosing a component (button, modal/sheet, tab bar, menu, form field, list, slider, toggle), implementing a UX pattern (onboarding, search, loading, feedback, notifications, navigation, settings, sign-in), or applying visual/UX foundations (color, typography, layout, spacing, dark mode, accessibility, motion, icons). Each skill maps an Apple HIG concept to concrete code on Web (HTML/CSS/ARIA), SwiftUI/UIKit, Android (Jetpack Compose/Material 3), React Native, and Flutter, with guidelines, cross-platform accessibility, and anti-patterns.
---

# Apple Human Interface Skills

Apple's Human Interface Guidelines, scraped in full and distilled into short, **multi-platform** design skill files an agent can apply directly when building **web or mobile** interfaces.

## How to use this skill

1. Identify what you're building — a **component**, a **pattern/flow**, a **foundation**, or an **interaction**.
2. Find it in the router below and read that one file (each is short and self-contained).
3. Every file has the same shape:
   - **Use it for** — when this applies
   - **Implementation** — a table mapping the concept to *Web (HTML/CSS/ARIA), SwiftUI/UIKit, Android (Compose), React Native, Flutter*
   - **Guidelines** · **Accessibility** · **Avoid**
   - **Full reference** — link to the complete Apple HIG page under `references/`
4. Apply the row for your target platform, plus the Accessibility and Avoid rules (they hold on every platform).

`skills/` holds **65** distilled skills. `references/` holds the **172** full HIG pages for deep dives.

## Router

### Foundations — Visual & UX principles — apply to every screen.

| Skill | Use it for |
| --- | --- |
| [Accessibility](skills/foundations/accessibility.md) | Building interfaces everyone can perceive, operate, and understand regardless of ability or c… |
| [Branding](skills/foundations/branding.md) | Expressing a recognizable brand identity while keeping the experience familiar and content-first |
| [Color](skills/foundations/color.md) | Use color deliberately to communicate status, express brand, convey hierarchy, and provide co… |
| [Dark Mode](skills/foundations/dark-mode.md) | A systemwide dark color palette for low-light viewing that users expect every app and site to… |
| [Icon Systems](skills/foundations/icon-systems.md) | A consistent, configurable library of symbols that align with your typography across all weig… |
| [Icons (Interface Icons / Glyphs)](skills/foundations/icons.md) | Simple graphic symbols that express a single action, item, or mode in a way people instantly … |
| [Images](skills/foundations/images.md) | Delivering artwork at the right format and resolution so it looks sharp on every display |
| [Inclusion](skills/foundations/inclusion.md) | Putting people first by using respectful language and imagery and presenting content everyone… |
| [Layout](skills/foundations/layout.md) | A consistent, adaptive layout grounds people in content and works across screen sizes and ori… |
| [Materials](skills/foundations/materials.md) | Translucent, blurred effects that separate a floating control/navigation layer from backgroun… |
| [Motion](skills/foundations/motion.md) | Purposeful, fluid animation that conveys status, gives feedback, and enriches the experience … |
| [Privacy](skills/foundations/privacy.md) | Being transparent about the data and device capabilities you need, and protecting whatever pe… |
| [Right to Left (RTL)](skills/foundations/right-to-left.md) | Mirroring your interface to match the reading direction of RTL scripts like Arabic and Hebrew |
| [Typography](skills/foundations/typography.md) | Typographic choices establish legibility, hierarchy, and brand through deliberate use of size… |
| [Writing](skills/foundations/writing.md) | The words in your interface — labels, messages, empty states, errors — are a core part of the… |

### Patterns — Recurring flows — wire these up end-to-end.

| Skill | Use it for |
| --- | --- |
| [Collaboration and Sharing](skills/patterns/collaboration-and-sharing.md) | Simple, responsive ways for people to share content and collaborate on it while communicating… |
| [Drag and Drop](skills/patterns/drag-and-drop.md) | Moving or copying content by dragging a selection from a source location to a destination |
| [Entering Data](skills/patterns/entering-data.md) | Designing form input so people can supply information quickly and without mistakes |
| [Feedback](skills/patterns/feedback.md) | Cues that tell people what's happening, the result of an action, and how to avoid mistakes |
| [File Management](skills/patterns/file-management.md) | Letting people create, open, save, browse, and preview documents and files within an app |
| [Launching](skills/patterns/launching.md) | The startup experience from open to first interactive screen — ideally instant |
| [Loading](skills/patterns/loading.md) | Handling waits for content so they don't disrupt the experience — ideally finishing before pe… |
| [Managing Accounts](skills/patterns/managing-accounts.md) | Authentication and account flows that let people access their content without becoming a barr… |
| [Modality](skills/patterns/modality.md) | Content shown in a dedicated mode that blocks interaction with the rest of the app until expl… |
| [Notifications](skills/patterns/notifications.md) | Timely, permission-gated messages that inform people of events, delivered respectfully withou… |
| [Offering help](skills/patterns/offering-help.md) | Contextual help — tips, tooltips, and links — offered when an interface isn't fully self-expl… |
| [Onboarding](skills/patterns/onboarding.md) | A fast, optional flow that helps people get a quick start using your app |
| [Ratings and Reviews](skills/patterns/ratings-and-reviews.md) | Asking people for feedback on your product at the right moment, without nagging |
| [Search](skills/patterns/search.md) | Lets people find content within your app, optionally scoped or filtered |
| [Settings](skills/patterns/settings.md) | A place for general, infrequently changed preferences that customize the experience |
| [Undo and Redo](skills/patterns/undo-and-redo.md) | Letting people reverse and re-apply recent actions so they can explore and recover from mista… |

### Components — UI building blocks — pick the right one + correct semantics.

| Skill | Use it for |
| --- | --- |
| [Action Sheets](skills/components/action-sheets.md) | An action sheet presents a set of choices related to an action the user just initiated, typic… |
| [Alerts](skills/components/alerts.md) | An alert is a modal dialog that delivers critical information and requires the user to respon… |
| [Boxes](skills/components/boxes.md) | A box visually groups logically related content and controls, set off by a border or background |
| [Buttons](skills/components/buttons.md) | A button initiates an instantaneous action, combining style, content (text and/or icon), and … |
| [Charts](skills/components/charts.md) | A chart organizes data visually to highlight key insights and help people understand and decide |
| [Color Pickers](skills/components/color-pickers.md) | A color picker (Apple "color well") lets people choose and adjust a color for text, shapes, o… |
| [Combo Boxes](skills/components/combo-boxes.md) | A combo box combines a text field with a dropdown list, so people can type a custom value or … |
| [Context Menus](skills/components/context-menus.md) | A context menu provides quick access to actions relevant to a specific item or view, revealed… |
| [Disclosure Controls (Expand/Collapse)](skills/components/disclosure-controls.md) | Controls that reveal or hide related information or functionality, keeping advanced or second… |
| [Embedded Content](skills/components/embedded-content.md) | Embedded content loads and displays external rich web content (HTML, sites, media) inline wit… |
| [Labels](skills/components/labels.md) | A label is static, uneditable text that people can read (and often copy) but not edit |
| [Lists and Tables](skills/components/lists-and-tables.md) | Lists and tables present data in rows (and optionally columns), supporting scanning, selectio… |
| [Menus](skills/components/menus.md) | A menu reveals a list of commands, options, or states when the user activates a trigger, pres… |
| [Pickers](skills/components/pickers.md) | A picker presents one or more scrollable lists of distinct values to choose from, including d… |
| [Popovers](skills/components/popovers.md) | A popover is a transient view anchored to a control that appears above other content when cli… |
| [Progress Indicators](skills/components/progress-indicators.md) | Progress indicators show that an app is working during loading or a lengthy operation, option… |
| [Scrolling (Scroll Views & Sticky Headers)](skills/components/scrolling.md) | A scrollable region lets people view content larger than its container by moving it verticall… |
| [Search Fields](skills/components/search-fields.md) | A search field is an editable text field, with a search icon and clear button, that lets peop… |
| [Segmented Controls](skills/components/segmented-controls.md) | A segmented control is a linear set of two or more equal-width segments, each acting as a but… |
| [Select Menus](skills/components/select-menus.md) | A select menu (Apple "pop-up button") displays a menu of mutually exclusive options and updat… |
| [Sheets](skills/components/sheets.md) | A sheet presents a focused, self-contained task closely related to the current context, layer… |
| [Sidebars (Side Navigation / Drawer)](skills/components/sidebars.md) | A panel on the leading (left) side of a view for navigating between app areas or top-level co… |
| [Sliders](skills/components/sliders.md) | A slider is a track with a draggable thumb that people adjust between a minimum and maximum v… |
| [Split Views (Master–Detail / Multi-Pane Layout)](skills/components/split-views.md) | A layout of two or three adjacent panes where selecting an item in one pane updates the conte… |
| [Steppers](skills/components/steppers.md) | A stepper is a two-segment control (increment/decrement) for changing a value by a fixed amount |
| [Tab Bars (Primary / Bottom Navigation)](skills/components/tab-bars.md) | A persistent bar of top-level destinations that lets people switch between the main sections … |
| [Text Fields](skills/components/text-fields.md) | A text field is a rectangular area where people enter or edit a small, specific piece of text… |
| [Toggles](skills/components/toggles.md) | A toggle lets people choose between a pair of opposing states (on/off), using a distinct appe… |
| [Toolbars](skills/components/toolbars.md) | A horizontal bar of frequently used commands, controls, navigation, and search along the top … |
| [Windows](skills/components/windows.md) | A window is the bounded surface that presents an app's content; on the web it maps to the bro… |

### Interaction — Input & focus — keyboard, pointer, touch, selection.

| Skill | Use it for |
| --- | --- |
| [Focus and Selection](skills/interaction/focus-and-selection.md) | Focus visually marks the element an interaction targets; selection marks the item(s) a user h… |
| [Keyboard](skills/interaction/keyboard.md) | Physical-keyboard input for text entry, shortcuts, and navigating an interface without a pointer |
| [Pointer and Hover](skills/interaction/pointer-and-hover.md) | Mouse and trackpad input for precise navigation, hover feedback, and contextual (right-click)… |
| [Touch and Gestures](skills/interaction/touch-and-gestures.md) | Physical motions — tap, swipe, drag, pinch — that directly manipulate on-screen objects on to… |
