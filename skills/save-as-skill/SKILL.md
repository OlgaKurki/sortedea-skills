---
name: save-as-skill
description: Package a finished playbook, voice profile or LinkedIn house rules into an installable skill and hand back a zip. Use after one of those skills has produced a document about a principal.
---

# Save as skill

**Use this skill when** someone has finished building a document about their principal and wants it as an installable skill. Phrases that mean this skill: "package this as a skill", "save it as a skill", "turn this into a skill", "make this a skill I can install", "zip this up as a skill", or simply "save as skill" after running executive-playbook, executive-voice or linkedin-ghostwriting.

Your job is to do the whole packaging job for them. They should have to answer one question, and then receive a zip file. Do not teach them the format, do not walk them through the steps, and do not hand back instructions for them to follow. Build it.

## What you are packaging

Find the source material first. In order of preference:

1. A document produced earlier in this conversation
2. A file the user has attached or pointed at
3. A file in the working folder or project

If you cannot find it, ask once which document they mean, and stop until they answer. Never invent the content.

Work out which of the three it is, because the exclusions differ:

| Source | Becomes | The exclusion that matters |
|---|---|---|
| Executive Playbook operating file | `playbook-<name>` | Everything in the private annex |
| Executive Voice profile | `voice-<name>` | Samples that still carry real names or figures |
| LinkedIn house rules | `linkedin-<name>` | Their login, anything not yet public |

If the document is something else entirely, package it anyway using the same method, and pick a sensible prefix.

## Step 1. Ask for the name

Ask one question: **what should this be called?**

Suggest a default in the answer, built from the principal's name as it appears in the document: `voice-jchen`, `playbook-mrivera`. Tell them they can just say yes.

Then validate silently and fix without fuss:

- Lowercase only. Convert capitals rather than complaining.
- Letters, numbers and hyphens only. Replace spaces and underscores with hyphens.
- 64 characters maximum.
- **It cannot contain the words `claude` or `anthropic`.** Both are reserved. If they ask for one, say so and propose an alternative.

If they give you a name that needed changing, show them what you used and why, in one line.

## Step 2. Strip before you build

**Do this before writing anything, and do not skip it because the material is already in the conversation.**

These skills sit alongside documents holding a principal's private details, and the packaged skill is a file that gets uploaded, copied and eventually shared. Anything you carry across is out of the user's sight from that point on.

Remove, always:

- **Credentials of any kind.** Passwords, PINs, recovery codes, security answers. If the source contains one, leave it out and tell the user plainly that you did.
- **Private annex material.** Date of birth, home and secondary addresses, family members, personal contacts, medical contacts and hospitals, passport and visa details, loyalty numbers, card and payment details.
- **Real names, figures, clients and deal details inside writing samples.** Replace with placeholders: `Can you get me the [figure] before [day]?` The sample carries the voice; the content is not needed.
- **Anything about a third party** that is not needed to do the work.

Where the skill genuinely needs to know a thing exists, keep a pointer and not the value: *"passport details are in the annex, ask me"*.

Keep a list of what you removed. You will show it at the end.

## Step 3. Build the folder

```
<name>/
├── SKILL.md
└── references/
    ├── <long material>.md
    └── log.md
```

**Into `SKILL.md`** goes everything that should apply to every piece of work: the rules, the measurements with their numbers intact, the register or scheduling tables, what never appears, the hard nos.

**Into `references/`** goes everything long or occasional: verbatim samples, restaurant and gift lists, post archives. Create `log.md` with a table for corrections, ready to fill in.

Write the frontmatter:

```yaml
---
name: <the validated name>
description: <under 200 characters, no colon>
---
```

The description decides whether the skill ever fires, so write it around what this person will actually type. "How J Chen writes. Apply when drafting anything going out under their name." **Never put a colon in it** unless the whole value is quoted, because an unquoted colon breaks the file and the skill fails to load silently.

Convert the document into instructions as you go. Imperative, not descriptive: *"Mean sentence length 14 words"* becomes *"keep sentences short, around 14 words"*. Keep every number. Keep any `[HARD]` and `[STRONG]` labels, and any `[said]`, `[observed]`, `[inherited]` tags, and explain at the top what they mean.

Add a line pointing at the references so they get read: *"when a draft feels wrong, read `references/samples.md` and match the rhythm of the real examples."*

End the body with these two rules, always:

> Matching the voice or the preference never justifies changing a fact, softening a decline, or committing them to something they did not say.
>
> Do not force every pattern into every piece of work. If it reads as an imitation rather than as them, use fewer of the patterns.

## Step 4. Check it before zipping

Run these yourself. Do not ask the user to.

- `name` is lowercase, hyphenated, 64 characters or fewer, and free of the reserved words
- `name` matches the folder name
- `description` is 200 characters or fewer and contains no unquoted colon
- The frontmatter parses as valid YAML
- No credential, annex item or unstripped sample survived step 2
- Every reference file you created is actually pointed at from `SKILL.md`

If a check fails, fix it and run it again.

## Step 5. Zip it and hand it over

The zip must contain **the folder**, not the loose files. A zip with `SKILL.md` at the top level is rejected on upload.

```bash
zip -r <name>.zip <name>/
```

Deliver the zip file to the user.

## Step 6. Tell them three things, briefly

1. **How to install it.** Customize, then Skills, then Add, then "Upload a skill". Then switch it on, because uploading and enabling are separate.
2. **What you left out**, as a short list. This is not optional. They need to know their principal's home address is not in the file, and equally that it is therefore not available to the skill.
3. **One line on keeping it current.** When their principal changes something they drafted, add it to `references/log.md`. Each quarter, anything that has happened three times becomes a rule.

Keep all of this to a few lines. They asked for a file, not a lesson.

## Never do these

- **Never publish it, share it organisation-wide, or suggest either.** This is a file about a named real person built from their private material. Personal use, or one named colleague who covers for them.
- **Never carry a credential across**, however it is framed, including "just so the skill knows".
- **Never invent content** to fill a gap in the document. A thin skill built from a thin document is honest. Write `— not yet known` and move on.
- **Never hand back instructions instead of a file.** If you cannot build it, say what is blocking you.
