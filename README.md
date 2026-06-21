<p align="center">
  <img src="https://docs-assets.developer.apple.com/published/fcb6f603e6672e3443637efe652e5bdb/platforms-iOS-intro%402x.png" width="620" alt="Apple platforms">
</p>

# Apple Human Interface Skills

Apple's Human Interface Guidelines are some of the best design writing out there, but they're spread across ~170 web pages. I wanted that thinking in a form an AI could actually follow while designing something, so I scraped the whole thing and boiled the useful parts down.

The goal is simple: give an agent good design taste. Not "use this component," just Apple's principles for what makes an interface clear, calm, and easy to use.

## What's here

Every HIG page, pulled down and turned into Markdown, plus a short distilled file for each design topic. Each one says what the thing is, when it's the right choice, the guidelines to follow, the accessibility points to keep in mind, and the mistakes to avoid.

It's design guidance on purpose — it tells you how something should look and behave, never which framework or code to build it with. That part's up to you.

## Layout

```
SKILL.md      the entry point: a short intro and a table that points to the right topic
skills/       65 short design skills — foundations, patterns, components, interaction
references/   the full 172-page HIG, for when you want everything Apple wrote
```

## Using it

Point an AI agent at `SKILL.md`. It reads the router, jumps to the one topic it needs (designing a modal? open `sheets.md`), and applies the guidance. Each skill links back to the original Apple page if you want the full version.

## Credit

Everything here is from Apple's [Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines) — I just scraped it (June 2026) and reorganized it. It's Apple's work; this is an unofficial reference, and the image up top is theirs too.
