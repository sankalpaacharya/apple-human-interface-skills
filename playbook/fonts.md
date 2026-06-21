# Fonts for an Apple look

Typography is half the "feel." Apple uses **San Francisco** (SF Pro) everywhere, with **New York** as the serif and **SF Mono** for code. You usually cannot ship SF Pro on the open web (Apple's license limits it mostly to Apple-platform development), so the move is: use the real system font where it exists for free, and a close open substitute everywhere else.

## The default: system font stack

On Apple devices this renders actual San Francisco at zero cost and zero download. Everywhere else it falls back gracefully.

```css
font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
```

Use this when you want "native on Apple, fine elsewhere" and don't want a font download.

## The cross-platform substitute: Inter

[Inter](https://rsms.me/inter/) (free, open, OFL) is the standard stand-in for SF: similar proportions, large x-height, excellent screen legibility. Use it when you want the *same* look on every device, not just Apple's.

```css
font-family: "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
```

Install: `npm i @fontsource/inter` (self-host) or load from Google Fonts. Turn on the optical-sizing / display cut for headings if you can.

Other solid SF-like options: **Geist** (Vercel), **Albert Sans**, **Figtree**.

## Monospace (code, numbers)

```css
font-family: ui-monospace, "SF Mono", "JetBrains Mono", Menlo, Consolas, monospace;
```

`ui-monospace` pulls SF Mono on Apple for free. **JetBrains Mono** is a great open fallback.

## Serif (editorial / New York vibe)

Apple's New York isn't freely web-licensed either. Closest open options: **Newsreader**, **Source Serif 4**, **Fraunces** (more characterful).

## Tips that make type feel Apple

- Set body text to **17px**, not 14-15. Apple text runs larger than typical web defaults.
- Build hierarchy with **weight and color**, not just size. Semibold headlines, regular body, secondary-gray captions.
- Keep line-height generous (about 1.3 on body) and measure narrow (60-75 chars).
- Use **few sizes** (see the type ramp in `tokens.md`). Restraint reads as polish.
- Slightly tighten letter-spacing on large titles (-0.02em); leave body at default.
- Enable system features: `font-feature-settings: "cv11"` style tweaks are optional, but turning on proper kerning and ligatures helps.

## Quick answer: should I add fonts?

Yes. Pick one:
- Want it free and native-feeling on Apple, low effort -> **system font stack**.
- Want it identical on every platform -> **self-host Inter** + system stack fallback.

Either way, wire the family into a token (see `tokens.md`) so the whole UI uses it consistently.
