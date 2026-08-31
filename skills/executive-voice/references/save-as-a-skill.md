# Saving the profile as a skill

The finished profile is a document. Turning it into a skill is what makes it get used, because from then on it applies itself whenever anyone drafts in that person's name instead of waiting to be remembered and opened.

Takes about 20 minutes.

## Read this first

A voice skill is a file about a named real person, assembled from their private correspondence.

- **Never publish it.** Not to a public repository, not to a skills directory, not to a shared marketplace. This applies even with names removed, because a voice profile is identifying by construction.
- **Never share it organisation-wide.** On Team and Enterprise plans, skills can be shared with a group or the whole company. This is not one of those. Personal only, or shared with the one named colleague who covers for you.
- **Strip the samples again before packaging.** You did this when you built the profile. Do it once more when you package, because the samples are the part most likely to carry a client name, a figure or a sentence about a person.
- **Tell your principal it exists in this form.** They agreed to a profile. Say that it is now something that runs automatically when you draft, and that you can delete it whenever they want.
- **Delete it when you leave.** It is not yours to take, and it is not the next assistant's to inherit without the principal agreeing again.

If your organisation has rules about where material relating to a named individual can live, those rules apply to this file.

## Structure

A skill is a folder with a `SKILL.md` in it, and optionally reference files that load only when needed.

```
voice-jchen/
├── SKILL.md          the working rules, the part that is always read
└── references/
    ├── samples.md     verbatim examples
    └── log.md         corrections over time
```

Split it this way because everything in `SKILL.md` loads into the conversation every time the skill fires, while reference files are read only when they are needed. Keep `SKILL.md` to the rules you want applied to every draft. Push the long material out.

**In `SKILL.md`:** the three-line summary, the measurements, openings and closings, signature vocabulary, the mechanics, how they handle declines and chases and bad news, the register table, what never appears, and the hard nos.

**In `references/samples.md`:** all the verbatim examples. These are what fix a draft that has come out wrong, and reading three real sentences beats re-reading the analysis, but they do not need to be in context for every message.

**In `references/log.md`:** the corrections log. Grows forever, needed rarely.

## Naming

The `name` in the frontmatter must exactly match the folder name, be lowercase, and use only letters, numbers and hyphens.

Use a convention that survives a second principal: `voice-jchen`, `voice-mrivera`. Do not call it `voice` or `my-boss`, because the day you support two people you will not know which is which, and neither will Claude.

Avoid the person's full name in the folder if the file might ever be seen by someone who should not connect the two.

## Writing the frontmatter

```yaml
---
name: voice-jchen
description: How J Chen writes. Apply when drafting any email, message or note that will go out under their name, or when checking whether a draft sounds like them.
---
```

Two limits. The name is capped at 64 characters. **The description is capped at 200 characters in the Claude app**, and it is the only thing Claude reads when deciding whether to fire the skill, so it has to name both what it is and when to use it. Do not put a colon in it unless you quote the whole line, because an unquoted colon breaks the frontmatter and the skill will silently fail to load.

Write the description so it triggers on what you actually say. If you say "draft a reply to Marcus" rather than "apply the voice profile", the description needs "drafting", "reply" and "in their name" in it.

## Writing the body

Convert the profile into instructions. Same content, imperative mood.

The profile says: *Mean sentence length 14 words in internal email.*
The skill says: **Keep internal email sentences short, around 14 words. Long, clause-heavy sentences do not sound like them.**

Keep the rule strengths. A skill that applies every tendency at full force produces parody, so carry the labels across and say what they mean at the top:

> **[HARD]** never violate. **[STRONG]** most of the time. Everything else is a light preference that context can override.

Keep the numbers. "Prefers short sentences" is not actionable; "around 14 words, measured across 31 emails" is. The measurements are what make this better than a vibe.

Point at the reference files explicitly, so they get read when they are needed:

> When a draft feels wrong, read `references/samples.md` and match the rhythm of the real examples rather than re-reading these rules.

End the body with the two rules that stop it going wrong:

> Matching the voice never justifies changing a fact, softening a decline, or committing them to something they did not say.
>
> Do not force every pattern into every draft. If it reads as an imitation rather than as them, use fewer of the patterns.

## Packaging and installing

**In the Claude app.** Zip the folder, not the files. The zip must contain `voice-jchen/` with `SKILL.md` inside it, not a loose `SKILL.md` at the root. Then Customize, then Skills, then Add, then "Upload a skill". Check it is switched on afterwards.

**In Claude Code or a similar tool.** Drop the folder into `~/.claude/skills/` for personal use, or `.claude/skills/` inside a project.

**Do not install it by pasting the text** into the "Write skill instructions" option. That works for a single-file skill, but it flattens the reference files into one block and you lose the reason for splitting them.

## Test it

Draft three things you have already sent, and compare. Then run the mixed sample test from the main skill: three drafts of yours against three real ones, shown to someone who knows the principal.

If the skill does not fire when you expect it to, the description is wrong, not the body. Rewrite the description using the words you naturally say.

## Keeping it current

The corrections log is the engine. Every time a draft comes back edited for voice rather than content, add the before, the after and the rule to `references/log.md`.

Once a quarter, read the log and promote anything that has happened three times into a rule in `SKILL.md`. That is the whole maintenance routine, and it is why the skill gets better rather than staler.

Re-run the corpus measurement once a year, or after anything that changes how someone writes: a new role, a new board, a merger, a bad quarter.

## More than one principal

One skill each, named clearly, each with its own samples and log. Do not build a single skill that tries to hold two voices, because the descriptions collide and you get the wrong one at the worst moment.

If you cover for a colleague's principal occasionally, keep that skill switched off until you need it.
