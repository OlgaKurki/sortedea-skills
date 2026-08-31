# SortedEA Skills

Agent Skills for executive assistants, PAs, chiefs of staff and anyone in a support function.

Built by a working EA, for working EAs. Part of [sortedEA.club](https://sortedea.club).

Most "AI for assistants" tooling is either a sales CRM with the labels changed, or a prompt someone wrote after reading a job description. These skills come from the actual job — the templates, checklists and judgement calls that get used with real principals.

## Install

```bash
npx skills add OlgaKurki/sortedea-skills
```

Or a single skill:

```bash
npx skills add https://github.com/OlgaKurki/sortedea-skills/tree/main/skills/executive-playbook
```

Works with Claude Code, Cursor, and anything else that reads `SKILL.md`. For claude.ai, zip the skill folder and upload it under Settings → Capabilities → Skills.

## Skills

### `linkedin-ghostwriting`

Drafting a principal's LinkedIn posts and comments without breaching LinkedIn's account rules or producing the low-substance content it now demotes.

Two facts shape it, and most executive-LinkedIn advice ignores both.

**Ghostwriting is allowed. Account access is not.** Nothing in LinkedIn's rules requires anyone to compose their own posts — but signing in as your principal breaches the User Agreement outright, and a great many assistants do it. Company Pages have a proper admin model; personal profiles have no assistant seat at all. The skill gives three workflows that aren't a breach, including the official OAuth route compliant schedulers use, and the sentence to say when a principal offers you their password.

**Substance is now a ranking factor, and LinkedIn says so in writing.** The platform names "AI slop" as a category it demotes, with a member-facing report button. So the ghostwriter's failure mode has inverted: it used to be sounding wrong, and now it's sounding fine and saying nothing. The skill treats the work as extraction rather than composition — the voice note, the meeting harvest, the disagreement — and tells you to spike the post when there's nothing there. If you can't find a specific claim, a number, a named example or a real opinion, don't write it.

`references/platform-facts.md` separates what lasts (character limits, policy clauses) from what goes stale (ranking behaviour), marks each claim official or third-party, and dates them. It ends with a Folklore section for the advice repeated most confidently on the least evidence — optimal posting times, the golden hour, broetry, emoji penalties. The "links reduce reach" claim is filed as unproven in both directions rather than quietly picked.

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
