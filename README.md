# SortedEA Skills

Agent Skills for executive assistants, PAs, chiefs of staff and anyone in a support function.

Built by a working EA, for working EAs. Part of [sortedEA.club](https://sortedea.club).

Most "AI for assistants" tooling is either a sales CRM with the labels changed, or a prompt someone wrote after reading a job description. These skills come from the actual job — the templates, checklists and judgement calls that get used with real principals.

## Install

```bash
npx skills add sortedea/skills
```

Or a single skill:

```bash
npx skills add https://github.com/sortedea/skills/tree/main/skills/executive-playbook
```

Works with Claude Code, Cursor, and anything else that reads `SKILL.md`. For claude.ai, zip the skill folder and upload it under Settings → Capabilities → Skills.

## Skills

### `linkedin-ghostwriting`

Drafting an executive's LinkedIn posts and comments, without breaching LinkedIn's account rules or producing the content it now demotes.

Two facts shape it, and most advice on executive LinkedIn ignores both.

**Ghostwriting is allowed. Account access is not.** Nothing in LinkedIn's rules requires anyone to compose their own posts, but signing in as your principal breaches the User Agreement outright (§2.2, §8.2), and plenty of assistants do it. Personal profiles have no delegation model the way Company Pages do. The skill gives three compliant workflows instead, including the one official route: OAuth with the `w_member_social` scope, which the executive authorises themselves and can revoke.

**Substance is now a ranking factor and LinkedIn says so in writing.** Since 2026 it names "AI slop" as a demoted category, with a reader-facing report button and a warning that surfaces in the author's own analytics. The ghostwriter's failure mode has inverted: it used to be sounding wrong, and now it is sounding fine and saying nothing. So the skill treats the job as extraction rather than composition, with three methods for getting a real point of view out of a principal, and an instruction to say there is nothing to post this week when there isn't.

The reference file separates durable facts (limits, policy, the delegation route) from perishable ones (ranking behaviour), grades every claim by source, and debunks the folklore. The link-penalty belief is unproven in both directions; the real documented constraint is that a post carries a link preview or an image, not both.

### `executive-voice`

Builds a voice profile of a principal from their real writing, so anything drafted in their name sounds like them.

Runs the opposite way round from the usual voice-capture interview. Your principal will not sit through 100 questions about their punctuation, and people describe their own writing badly. So the corpus is the source of truth and the assistant is the source of context: read 25 to 40 real pieces, measure them, then answer roughly 20 questions about what writing cannot reveal.

Four things it insists on:

- **Exclude anything that passed through someone else.** LinkedIn posts, press quotes, bylined articles, official statements. Comms teams and agencies write a great many of them, you usually cannot tell by reading, and one contaminated source teaches the wrong voice. The rule is exclusion, not caution.
- **Count, don't sense.** You will believe they write short sentences and find the mean is 24 words. Absence is the strongest evidence of all: no exclamation mark in 40 emails is a harder rule than anything you could be told.
- **Tell them you're doing it.** Building a model of how someone writes from their private correspondence is not a thing to do quietly, and they will improve it in five minutes anyway.
- **Turn the finished profile into a skill.** A profile in a folder gets read once. Installed as a skill, it applies itself every time anyone drafts in that person's name. The guide covers what belongs in the instructions against the reference files, naming when you support more than one principal, packaging, and the corrections loop that keeps it current.

Ships with an extraction checklist, the gap questions, a profile template with a "what I got wrong" log, and the save-as-a-skill guide.

**A voice skill is never shareable.** It describes a named real person and is built from their correspondence. It does not go to a public repo, an organisation-wide skill directory, or the next assistant without the principal agreeing again. The repo's `.gitignore` blocks the obvious filenames, but that is a safety net, not permission.

### `sound-human`

Rewrites assistant and executive writing so it stops reading as AI, without stripping out the formality a document actually needs.

Most de-AI advice is written for blog posts: use contractions, cut the formality, write punchy. Applied to a board minute or a decline to an investor, that produces something worse than the AI draft. So this one starts from a register map instead of a voice. Formality is not the tell. Formula is.

It covers the tells that show up in support writing specifically, which are not the ones in marketing AI-speak: "I hope this email finds you well", stacked hedges, reflexive apology for chasing, "at your earliest convenience", manufactured consensus in minutes. Plus em dashes, digits, and sentence rhythm.

Two rules it holds harder than the style guide:

- **Nothing factual moves during a style pass.** No number, name, date, deadline, decision or commitment changes, and nothing is added that was not in the source. Making a draft warmer must not make it promise more.
- **Warmth is not an AI tell.** The common failure is stripping every courtesy and producing something curt, which for an assistant is a professional risk. Cut formulaic warmth ("hope you're well"), keep specific warmth ("hope Lisbon went well").

Ships with 6 worked before/afters: declining a meeting, chasing a signature, an internal announcement, a briefing note, minutes, and a travel confirmation. The minutes example shows the over-correction failure as well as the original.

### `meeting-minutes`

Turns a transcript or rough notes into circulation-ready minutes: numbered decisions, a four-column action table with named owners, and an honest list of what it could not work out.

Built around one principle — a draft that flags its own gaps saves more time than a draft that quietly fills them in. It will not invent an owner, guess a deadline, or attribute words to someone the source doesn't clearly show said them. Disagreements stay recorded as disagreements.

It also flags anything that may not suit the full circulation list — performance discussions, compensation figures, privileged legal advice, unannounced commercial matters — under **Flagged for circulation review**, so the minute taker decides rather than the tool.

### `executive-playbook`

The operating manual for one principal — how they work, travel, communicate and decide. Builds it by interview, keeps it current as preferences change, and serves it to every other task so drafting, travel and diary decisions start from fact instead of guesswork.

Derived from a playbook template used with real principals over several years, and structured so an assistant can hand it to a cover without handing over the person's private life.

**What makes it different:** it sorts every fact into three tiers before writing anything down.

| Tier | What | Where |
|---|---|---|
| Operating | How they work — hours, meeting style, seat preference, who gets through | The file agents read |
| Private annex | Identity, addresses, family, medical, loyalty numbers | Held like a personnel file. Never pasted into an AI tool |
| Never recorded | Passwords, PINs, recovery codes | A password manager with delegated access |

That third tier is the point. Assistants get asked to keep credential lists, and it feels helpful right up until the file leaks — at which point the person who typed it is where the investigation starts. The skill refuses, and gives you the sentence to say instead.

It also tags every fact `[said]` / `[observed]` / `[inherited]`, because roughly half of what any assistant knows about their principal is inferred, and a cover assistant can't tell the difference unless you mark it.

<details>
<summary>What's in it</summary>

```
skills/executive-playbook/
├── SKILL.md
├── references/
│   ├── question-bank.md            # the interview, 11 sections
│   ├── sensitivity-tiers.md        # sorting rules and the awkward cases
│   └── consuming-the-playbook.md   # how other skills should read it
└── assets/
    ├── playbook-template.md        # the operating file
    └── private-annex-template.md   # the annex structure
```
</details>

## Roadmap

Gaps found in a survey of the existing skills landscape — nothing credible covers these yet:

- **`board-pack`** — the pack as an artefact: agenda, consent items, pre-reads, version control, distribution
- **`trip-file`** — corporate travel, not holiday planning. Confirmation numbers, visas, disruption handling
- **`relationship-map`** — a principal's network, tended rather than pipelined
- **`slot-politics`** — diary triage as judgement, not free/busy
- **`new-joiner-runway`** — the EA's real onboarding checklist

## A note on privacy

These skills handle information about real people who did not choose to be in an AI system. Every skill here is built on that assumption. If you find somewhere one of them encourages recording something it shouldn't, please open an issue — that's a bug, and a serious one.

## Contributing

Issues and pull requests welcome, particularly from working assistants. If a skill doesn't match how the job actually goes in your organisation, that's the most useful thing you can tell us.

## License

MIT — see [LICENSE](LICENSE).
