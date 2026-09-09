# Saving it as a skill, by hand

Only needed if you do not have `save-as-skill` installed. With it, say "save as skill" and skip this page.

## The folder

```
voice-yourname/
├── SKILL.md              rules, loaded every time
└── references/
    ├── samples.md        verbatim examples
    └── log.md            corrections over time
```

Everything in `SKILL.md` loads into the conversation whenever the skill fires. References sit on disk until something needs them. So the rules go in the first, the long material in the second.

## The frontmatter

```yaml
---
name: voice-yourname
description: How I write. Apply when drafting anything going out under my name, or checking whether a draft sounds like me.
---
```

**Two things break silently here.**

The `name` must be lowercase letters, numbers and hyphens, 64 characters maximum, and it cannot contain the words `claude` or `anthropic`, which are reserved.

The `description` must be **200 characters or fewer** in the Claude app, and **must not contain a colon** unless the whole value is quoted. An unquoted colon breaks the file and the skill fails to load with no error and no warning. It simply never fires.

Write the description around the words you actually type. If you say "draft a reply to Marcus", the description needs "draft", "reply" and "as me" in it.

## The body

Convert the profile into instructions. Imperative, not descriptive.

> **Profile:** mean sentence length 14 words in messages.
> **Skill:** keep messages short, around 14 words a sentence. Long clause-heavy sentences do not sound like me.

Keep the numbers. Keep the strength labels, and explain them at the top. Point at the samples so they get read:

> When a draft feels wrong, read `references/samples.md` and match the rhythm of the real examples rather than re-reading these rules.

End with:

> Sounding like me never justifies changing a fact, softening a commitment, or agreeing to something I did not agree to.
>
> Do not force every pattern into every draft. If it reads as an imitation rather than as me, use fewer of the patterns.

## Install it

Zip **the folder**, not the files inside it. A zip with a loose `SKILL.md` at the top level is rejected.

Claude app: Customize, then Skills, then Add, then "Upload a skill". Then switch it on, because uploading and enabling are two different things.

Claude Code: drop the folder into `~/.claude/skills/`.

## Keep it current

Add every correction to `references/log.md`. Once a quarter, anything that has happened three times becomes a rule in `SKILL.md`. Fifteen minutes.
