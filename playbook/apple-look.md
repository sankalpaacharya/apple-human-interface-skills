# Make it look Apple

The HIG files in `skills/` give you taste and correctness. This file is the opinionated layer: the concrete moves that make a UI read as "Apple," and how to actually get there instead of a timid spacing pass. Pair it with the numbers in `tokens.md` and the type setup in `fonts.md`.

## What actually reads as "Apple"

- **Restraint.** One accent color, used sparingly (primary action, selection, links). Everything else is black/white and a gray ramp. Resist extra colors.
- **Generous whitespace.** Apple layouts breathe. When unsure, add space. Tight, cramped layouts never feel Apple.
- **Strong, simple hierarchy.** A clear focal point per screen. Big confident headings (Semibold/Bold), calm secondary text in gray. Hierarchy from weight and color, not rainbow.
- **Soft, large corners.** Continuous-curve corners on cards, sheets, buttons. Pills for tags and segmented controls.
- **Depth through material, not borders.** Subtle shadows and translucency (blur) instead of hard 1px outlines everywhere. Separators are faint.
- **Type that's a bit larger than the web norm.** Body at 17. Few sizes. See `fonts.md`.
- **Spring-based motion.** Quick, soft, physical. Short fades and small scale/position shifts, never long linear slides. Always respect reduced-motion.
- **Alignment and grid.** Everything on an 8pt grid, optically aligned. Consistent side margins.
- **Content first.** Chrome recedes; the content is the interface. Avoid heavy toolbars and decoration.

## The Apple-look checklist

Run a design against this:

- [ ] One accent color only, used for the primary action and selection
- [ ] Body text 17px; headings use weight, not just size, for hierarchy
- [ ] Spacing is all multiples of 8 (4 for half-steps); layout has room to breathe
- [ ] Corners are soft and consistent (cards lg, buttons md, pills for tags)
- [ ] Shadows are subtle; separators are faint; no heavy borders
- [ ] One clear focal point; secondary info is gray and quieter
- [ ] Light and dark both look intentional
- [ ] Touch targets at least 44x44
- [ ] Motion is short, spring-like, and disabled under reduced-motion
- [ ] Contrast passes (4.5:1 body text); nothing relies on color alone

## How to use this skill so it's bold, not timid

The skill gives taste, but you supply the ambition. To get real change:

1. **Ask for it explicitly.** "Redesign this to feel premium and Apple-like. Rework hierarchy, type scale, spacing, color, and depth using the playbook tokens. Be bold, not minor tweaks."
2. **Adopt the tokens first.** Wire `tokens.md` into the project (CSS vars / Tailwind theme) and the font from `fonts.md`, then design against those names. "Consistent spacing" becomes real numbers.
3. **Give direction.** A reference screenshot or a vibe ("calm and editorial," "dense and pro") beats any amount of prose. Taste needs a target.
4. **Look, then critique.** Render the screen, screenshot it, and check it against the checklist above. Fix what's weak. Repeat. This loop is where polish actually happens; text-only edits can't see a timid heading.

## Common ways "Apple-like" attempts go wrong

- Too many accent colors, or the accent used on everything (kills hierarchy).
- Cramped spacing; nothing has room.
- Tiny body text and many font sizes.
- Hard borders and heavy shadows instead of subtle depth.
- Linear, slow animations instead of quick springs.
- A "checklist pass" that fixes spacing but never touches hierarchy, type, or color.
