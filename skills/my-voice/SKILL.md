---
name: my-voice
description: Capture how you actually write, from your own sent mail and posts, then save it as a skill so anything drafted for you sounds like you. For your own voice, not your principal's.
---

# My voice

**Use this skill when** someone wants to capture their own writing voice, says drafts do not sound like them, is about to start delegating their writing, or wants Claude to write as them rather than at them. Phrases that mean this skill: "capture my voice", "my writing style", "this doesn't sound like me", "write as me", "learn how I write", "build my voice profile".

This is the companion to `executive-voice`, pointed at yourself. The method looks similar and the traps are completely different.

When you build a profile of someone else, the hard part is getting evidence. When you build one of yourself, the evidence is easy and **you are the unreliable part**. You will describe the writer you intend to be. Almost everyone says they write short and direct; the corpus usually disagrees.

So the rule is the same and matters more: **the corpus decides, you only explain it.**

## Step 1. Gather what you actually wrote

Aim for 25 to 40 pieces, recent, across the range of things you write.

**Count only writing that went out as yours, unedited.**

| Use | Do not use |
|---|---|
| Sent email you wrote yourself | **Anything you drafted in someone else's voice** |
| Messages, Slack, WhatsApp | Anything a comms or marketing team edited |
| Documents you wrote alone | Collaborative documents |
| Your own posts, if you write them | Posts an agency or colleague wrote for you |
| Anything you wrote fast, on a phone | Anything you laboured over for a week |

**The first exclusion is the one that catches assistants.** If you draft for a principal, your sent folder is full of writing in their voice, not yours. Feed that in and you capture them. Filter to messages sent as yourself, to your own contacts, about your own work.

**Fast writing is the most honest.** A reply typed between meetings shows your defaults. A carefully polished document shows your effort.

## Step 2. Measure it

Work through `references/extraction-checklist.md`. Count, do not sense.

The point of counting is that you are about to be surprised. You will believe you write short sentences and find the mean is 23 words. You will believe you are warm and find that 14 of your last 20 emails open with the person's name and nothing else.

**Absence is the strongest evidence.** Something you have not done once in 40 pieces is a harder rule than anything you could tell yourself.

## Step 3. The mirror problem

You cannot hear your own tics. Nobody can. The word you overuse is invisible to you precisely because it sounds normal in your head.

So ask two people who read a lot of your writing:

- What do I always say?
- What would tell you a message was from me if my name was removed?
- Is there anything I do that annoys you?

That third question produces the most useful answer and the most uncomfortable one. Ask it anyway, of someone who will actually tell you.

Write their answers down verbatim. Do not tidy them.

## Step 4. Separate how you write from how you want to write

**This is the part that has no equivalent when you profile somebody else, and getting it wrong is the main way this skill fails.**

Capturing your principal's voice means recording it faithfully, tics and all. Capturing your own means you now have a choice, because you are the one who gets to change.

Sort every finding into three:

| | |
|---|---|
| **Keep** | This is me and it works. Protect it |
| **Keep, though it is a habit** | Harmless, distinctive, no reason to lose it |
| **Change** | I do this and I do not like it |

Then be strict about the last column. If you over-apologise, hedge every request, or open with two lines of throat-clearing, **do not encode it**. A voice skill built from an unexamined corpus will faithfully reproduce the things you were hoping to stop doing, forever, at scale.

Write the change items as instructions, not as observations:

> **Observed:** opens with an apology in 9 of 20 emails.
> **In the skill:** do not open with an apology. Say the thing.

But keep the bar high. Three or four changes at most. Cut too much and you produce a generic professional voice with your name on it, which is exactly what you were trying to avoid.

**The test for whether a change belongs on the list:** would you be pleased or embarrassed to see this pointed out in your writing? Embarrassed goes in the change column. Merely surprised does not.

## Step 5. Write the profile

Use `assets/voice-profile-template.md`.

Every claim carries evidence. "Prefers short sentences" is useless. "Mean 14 words in messages, 21 in documents, from 33 samples" can be acted on.

Label the strength of each rule, because a profile applied uniformly produces a parody of you:

- **Hard rule.** Never violate. Rare. Usually something absent across the whole corpus, or a change you have committed to.
- **Strong tendency.** Most of the time.
- **Light preference.** Context decides.

Keep 15 to 20 stripped verbatim samples with it. When a draft comes out wrong, reading three real sentences of yours fixes it faster than any amount of analysis.

## Step 6. Save it as a skill

A profile in a folder gets read once. Installed as a skill it applies itself every time something is drafted for you, which is the point.

Say **"save as skill"** and the `save-as-skill` skill will package it: it names it, splits the rules from the samples, strips what should not travel, and hands you a zip to upload.

If you do not have that installed, `references/packaging.md` has the manual version and the two things that break silently.

Name it `voice-yourname`. If you also keep a profile of a principal, the prefix keeps them apart.

## Step 7. Test it

**The blind test.** Write three short pieces with the skill on. Mix them with three real ones. Ask someone who knows your writing which are which. If they pick yours out immediately, ask what gave it away. That answer is the missing rule.

**The wince test, faster and more honest.** Read a draft it produced and ask: would I send this? Not "is this good", but "is this mine". The wince is information.

## Keeping it true

Voices move. New job, new audience, deliberate change, a year of writing differently.

**Log the corrections.** Every time you rewrite something the skill drafted, note what you changed. Those edits are the highest quality evidence you will ever get, and they arrive free.

**Re-measure once a year**, or after anything that changes how you write.

## Two things to be careful about

**Your corpus contains other people's words.** Your sent mail includes what colleagues and clients said, commercial detail, and things told to you in confidence. Strip every sample before it goes anywhere: replace names, figures and clients with placeholders. `Can you get me the [figure] before [day]?` carries your voice and discloses nothing.

**A voice skill is not a licence to send unread.** It makes a draft sound like you. It does not know what you meant, what you promised last week, or what you would never say to this particular person. Read it before it goes.

And the rule that outranks the rest: **sounding like you never justifies changing a fact, softening a commitment, or agreeing to something you did not agree to.**
