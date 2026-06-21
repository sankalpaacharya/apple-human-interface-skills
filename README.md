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

## Install

This repo is an [Agent Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills) — a folder with a `SKILL.md`. Installing it just means dropping that folder where your agent looks for skills.

**Claude Code** — clone it into your skills folder:

```bash
# every project:
git clone https://github.com/sankalpaacharya/apple-human-interface-skills.git \
  ~/.claude/skills/apple-human-interface-skills

# or a single project:
git clone https://github.com/sankalpaacharya/apple-human-interface-skills.git \
  .claude/skills/apple-human-interface-skills
```

Claude then loads it automatically whenever your request matches what it's for — "design this screen," "review my UI," "lay out a settings page." No command to remember.

**Any other agent (Cursor, your own tooling, etc.)** — clone the repo anywhere and tell the agent to read `SKILL.md` first. It routes itself from there.

## Using it

Once installed, you don't really "call" it — just ask your agent to design or review something and it pulls the relevant topic in. Under the hood it reads the router in `SKILL.md`, opens the one file it needs (designing a modal? `sheets.md`), and applies the guidance. Every skill links back to the original Apple page if you want the full version.

## Credit

Everything here is from Apple's [Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines) — I just scraped it (June 2026) and reorganized it. It's Apple's work; this is an unofficial reference, and the image up top is theirs too.
