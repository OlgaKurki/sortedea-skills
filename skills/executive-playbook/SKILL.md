---
name: executive-playbook
description: Build and maintain an Executive Playbook — how a principal works, travels, communicates and decides. Use before drafting, booking travel or making diary decisions on their behalf; when starting with a new boss or new principal; when onboarding as an EA, PA or Chief of Staff; or when capturing exec preferences you already carry in your head.
---

# Executive Playbook

**Use this skill when** an assistant is starting with a new principal, onboarding into an EA/PA/Chief of Staff role, capturing what they already know about their executive into something reusable, or asking how their principal likes their meetings, flights or updates. Also use it *before* drafting on a principal's behalf, prepping their travel, or triaging their diary — those tasks should read the playbook rather than guess. Phrases that mean this skill: "executive playbook", "principal profile", "new boss", "new principal", "exec preferences", "how does she like", "onboarding as an EA".

An Executive Playbook is the operating manual for one principal. It is the difference between an assistant who asks the same question three times and one who already knows the answer — and it is the substrate every other assistant skill should read from before it drafts, books, or schedules anything.

This skill does three jobs:

1. **Build** a playbook from scratch, by interview (new principal, or retrofitting one you already know well).
2. **Maintain** it — capture corrections as they happen, run periodic reviews.
3. **Serve** it to other skills and tasks, so drafting, travel and diary work start from fact instead of guesswork.

## Before anything else: the three tiers

A playbook contains material of wildly different sensitivity, and treating it as one document is the single most common mistake. Sort every fact into one of three tiers **as you collect it**. This is not bureaucracy — it decides what is safe to put in a file an AI assistant reads.

| Tier | What lives here | Where it goes | Who/what reads it |
|---|---|---|---|
| **1 — Operating** | How they work: hours, meeting style, comms preferences, seat and hotel preferences, briefing format, decision patterns, who gets through | `playbook.md` | You, cover assistants, and AI skills |
| **2 — Private annex** | Identity and personal life: date of birth, home addresses, family members, personal contacts, medical contacts, loyalty numbers, travel payment details | `playbook-private.md`, held wherever your organisation holds confidential HR-grade material | You, and a named backup. **Not** pasted into AI tools |
| **3 — Never recorded** | Passwords, PINs, access credentials, anything that authenticates as them | Nowhere. A password manager with delegated access | Nobody, via a document |

**On Tier 3, push back and mean it.** Assistants are routinely asked to keep a list of the principal's logins, and it feels helpful. It is the single highest-consequence document an assistant can create: it survives your handover, it gets emailed, it sits in Downloads. The correct answer is a password manager with emergency access delegated to you — 1Password, Bitwarden and Keeper all support this. If the principal insists on a document, say plainly that you'll set up the manager instead, and record in the playbook *that* this is where credentials live. Never transcribe a credential into `playbook.md`, `playbook-private.md`, or a chat with an AI assistant — including this one.

If the user tries to dictate credentials during the interview, stop them, explain in one sentence, and move on. Do not write them down "just for now".

For the full sorting rules, including the awkward middle cases, read `references/sensitivity-tiers.md`.

## Building a playbook

### Pick the mode

**Cold start** — new principal, day one, you know almost nothing. You'll build the playbook over the first 90 days. Prioritise Sections 2–5 (work, routine, scheduling, communication); everything else can wait until you've earned the standing to ask.

**Retrofit** — you've worked with them for months or years and it's all in your head. This is the more valuable mode and the more common one. The interview is a memory-extraction exercise, not a research task; you already know the answers.

**Handover** — you're leaving, or covering for someone. Build from the outgoing assistant's knowledge, and mark heavily what is inferred versus confirmed, because the incoming person cannot tell the difference and will act on both.

Ask which mode this is before starting. It changes the pacing and the order.

### Run the interview

Work through `references/question-bank.md` section by section. It maps to the eleven sections of the playbook.

Rules that make the difference between a useful playbook and a form nobody fills in:

- **One section at a time.** Ask the questions for a section, write that section, show it, move on. Never dump sixty questions at once — the user abandons it, and you get thin answers to all of them instead of good answers to some.
- **Write as you go.** After each section, append to the file. The interview must survive being interrupted, because it will be.
- **Skip freely.** "Don't know yet" is a valid answer and belongs in the file as `— not yet known` so the gap is visible. An empty row reads as "no preference"; an explicit gap reads as "ask them".
- **Mark the source of every fact.** This matters more than it sounds:
  - `[said]` — the principal told you directly
  - `[observed]` — you worked it out from how they behave
  - `[inherited]` — a previous assistant or colleague told you
  
  `[observed]` and `[inherited]` facts are the ones that turn out to be wrong, and they're the ones a cover assistant will act on with unearned confidence. Tag them.
- **Capture the reason, not just the rule.** "Doesn't take meetings before 10" is a rule you'll break the moment something looks urgent. "Doesn't take meetings before 10 — writes in the mornings and it's the only thinking time he gets" is a rule you'll defend. Ask *why* whenever the answer is short.

### Write the file

Use `assets/playbook-template.md` as the structure. Eleven sections, mirroring the classic EA playbook:

1. Personal profile · 2. Work profile · 3. Daily routine · 4. Scheduling guidelines · 5. Communication guidelines · 6. Travel and logistics · 7. Key relationships and networks · 8. Preferences and favourites · 9. Crisis and emergency plans · 10. Tech and tools · 11. Confidentiality protocols

Sections 1 and 9 are mostly Tier 2 — the operating file keeps a pointer, not the content. Section 10 splits: platforms and devices are Tier 1, access is Tier 3 and gets a pointer to the password manager.

Include the header block from the template verbatim. The "last reviewed" date is not decoration — a playbook nobody has touched in a year is actively dangerous, because it reads as current.

## Maintaining it

A playbook decays. Preferences change, direct reports leave, the hotel goes downhill. Two mechanisms keep it alive:

**Correction capture.** Whenever the principal corrects you — "actually I'd rather fly out the night before", "stop copying Marcus on these" — that is a playbook update, and it should happen the same day while you remember the exact wording. Treat every correction as a gift: it's a preference you didn't know you were guessing at. Update the line, change the tag to `[said]`, and note the date.

**Quarterly review.** Once a quarter, read the whole thing and check three things: what's now wrong, what's still `— not yet known`, and what's still tagged `[observed]` that you could just ask about directly. Fifteen minutes. Bump the "last reviewed" date whether or not anything changed, so the next reader knows it was checked.

**On handover**, walk the incoming assistant through it in person rather than emailing the file. The `[observed]` tags need explaining, and the things you deliberately left out need saying out loud.

## Serving it to other work

This is the part that earns the playbook its keep. Before any task that acts on the principal's behalf, read the relevant section first:

| Task | Read first |
|---|---|
| Drafting an email, message or reply as them | §5 Communication, §2 Professional preferences |
| Booking or building travel | §6 Travel and logistics, §3 Daily routine |
| Accepting, declining or moving a meeting | §4 Scheduling guidelines, §3 Daily routine |
| Building a briefing pack | §2 Work profile, §7 Key relationships |
| Ordering food, gifts or hospitality | §8 Preferences and favourites |
| Anything involving press, sensitive material or documents | §11 Confidentiality protocols |

When a task hits something the playbook doesn't cover, say so rather than inventing a preference — "the playbook doesn't record a seat preference for short-haul, want me to ask?" — and add the gap to the file. Guessing is how a playbook accumulates plausible fiction.

For the exact conventions other skills should use to read and cite the playbook, see `references/consuming-the-playbook.md`.

## What good looks like

A finished Tier 1 playbook is roughly two to four pages. It is specific enough that a competent stranger could cover for you for a week without calling you, and honest enough that they'd know which lines to double-check. It contains reasons as well as rules.

If it reads like a form someone filled in, it isn't finished.
