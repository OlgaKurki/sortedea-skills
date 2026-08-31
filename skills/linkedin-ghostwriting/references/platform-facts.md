# Platform facts

Checked 31 August 2026. Split deliberately into what lasts and what does not, because most LinkedIn advice mixes the two and goes stale within a year.

Source grades used below:
**[official]** LinkedIn Help, Legal, engineering blog, or a named LinkedIn product lead speaking in role
**[measured]** credible third party with a disclosed method
**[folklore]** widely repeated, no evidence found

---

## Durable: hard limits

All **[official]**, from LinkedIn Help.

| | Limit |
|---|---|
| Feed post | 3,000 characters |
| Article | 125,000 characters |
| Video | 15 minutes max, 5 GB, 3 seconds minimum on desktop |
| Images | 5 MB each, up to 20 in a multi-image post, aspect 3:1 to 4:5, 1080px wide recommended |
| Documents and carousels | 100 MB, 300 pages, PPT/PPTX/DOC/DOCX/PDF only |

Two things worth knowing about documents: they **cannot be edited after posting**, and viewers can download them as PDF. Check them harder than you check a post.

**The image-or-link rule, [official]:** "You can share either a URL link or an image in a post, but not both at the same time. For URL links, we create a preview image taken from the site being shared."

This is a real constraint with a real consequence. A post with a link gives up the image slot and gets whatever thumbnail the destination site provides. That is a sufficient reason to think about where a link goes, without needing to believe in a hidden penalty.

**Not officially documented:** comment length (1,250 characters is third-party consensus), headline (220), About section (2,600), connection note (300). Use the numbers, do not cite them as official. LinkedIn's own headline help page states no limit at all and is five years old.

---

## Durable: policy

**Account sharing is prohibited.** [User Agreement](https://www.linkedin.com/legal/user-agreement), effective 3 November 2025:

- §2.1 "you will only have one LinkedIn account, which must be in your real name."
- §2.2 "You will not share your account with anyone else."
- §2.2 "not share or transfer your account or any part of it."
- §2.2 "You are responsible for anything that happens through your account unless you close it or report misuse."
- §8.2 do not "use or attempt to use another's account (such as sharing log-in credentials or copying cookies)."
- §8.2 do not "Use bots or other unauthorized automated methods to access the Services… create, comment on, like, share, or re-share posts, or otherwise drive inauthentic engagement."

The [Professional Community Policies](https://www.linkedin.com/legal/professional-community-policies) repeat it and add: "Don't do things to artificially increase engagement with your content… don't agree with others ahead of time to like or re-share each other's content."

**Ghostwriting is not prohibited.** Nothing in the User Agreement or the Community Policies requires that a member composes their own posts. The rules govern account access and identity, not authorship. §3.6 even anticipates assisted content: "Please review and edit such content before sharing with others."

**The one sanctioned delegation route for a personal profile** is OAuth with the `w_member_social` scope, documented in LinkedIn's [Share on LinkedIn API](https://learn.microsoft.com/en-us/linkedin/consumer/integrations/self-serve/share-on-linkedin): "Required to create a LinkedIn post on behalf of the authenticated member." Compliant schedulers use this. The member authorises it on LinkedIn's own screen, no password moves, and access can be revoked.

**Company Pages are different.** They have real admin roles: super admin, content admin and others. Personal profiles have no equivalent. If your principal's activity could live on the Page instead, that is the properly delegable surface.

**AI-assisted content**, from LinkedIn's [best practices page](https://www.linkedin.com/help/linkedin/answer/a1481496), updated August 2026:

> "We do not want 'AI slop,' which refers to low-effort, likely AI-generated content that may sound polished on the surface but lacks a clear point of view, unique perspective, or substance."
> "LinkedIn's focus is not on how content is created, but whether it adds value… Content that feels generic, repetitive, or lacks a clear point of view is less likely to be widely distributed."
> "we recommend that you let others know (if it isn't obvious from the context) if you've relied heavily on AI to help create or modify the content."
> "You are ultimately responsible for everything you post on LinkedIn."

Members can report a post as "Seems like AI slop". Enough reports produce a tip in the author's own post analytics. It is feedback, not a policy strike.

---

## Perishable: how the feed currently behaves

Everything in this section can change without notice. Re-check it before you rely on it.

**What LinkedIn says it looks at**, from the engineering post [Engineering the next generation of LinkedIn's Feed](https://www.linkedin.com/blog/engineering/feed/engineering-the-next-generation-of-linkedins-feed) (March 2026) **[official]**:

- About the reader: their profile (industry, experience, skills, geography) and their behaviour over time, including "what you've read, liked, commented on, returned back to, or simply scrolled past".
- About the post: "format, author information (name, headline, company, industry), engagement counts, article metadata, and post text."
- Popularity is an explicit input: "posts that many people find valuable are more likely to be found as such to any given member."
- Matching is now semantic rather than keyword-based.

Two things follow that most advice misses. **The author's headline, company and industry are ranking inputs**, so keeping your principal's profile accurate is not vanity, it is distribution. And **hashtags, links, emoji, timing and line breaks do not appear anywhere in LinkedIn's own description of what the model reads.**

**What LinkedIn says it demotes**, from Tim Jurka, head of Feed, March 2026 **[official]**:

- Engagement bait, his example being "Comment 'Yes' if you agree".
- "recycled thought leadership posts that don't say much in terms of substance".
- Video decoupled from its caption.
- Engagement pods and comment automation, "including the use of third party software or browser extensions, which are not allowed on LinkedIn".

**Hashtags**, from Rishi Jobanputra, head of product, July 2025 **[official]**:

> "So what's the deal with hashtags? Do I need to use them? So the short answer is no, they are nice to have, not a need to have… we used to have a hashtag feed in the past, but people weren't really using it. So we're actually in the process of getting rid of it. Now where hashtags can come in useful is when people are trying to search for a specific trend or a topic."

Hashtag following and hashtag feeds are gone. One to three genuinely on-topic tags are a search aid and cost nothing. Stuffing is pointless.

**Dwell time.** LinkedIn published a model in 2020 that reduces a post's score in proportion to how likely a reader is to skip it, where dwell begins "when at least half of a feed update is visible" **[official]**. They never published the skip threshold, and the post is six years old. Anyone quoting a target in seconds is inventing it.

**The "see more" cut.** Around 210 characters on desktop and 140 on mobile **[measured]**, never documented by LinkedIn and certain to drift. Treat it as a principle rather than a number: the first two or three lines must earn the click.

---

## Folklore

**Links in posts reduce reach.** The most confidently repeated claim in LinkedIn advice, and **unproven in both directions**. LinkedIn has never confirmed it. It is absent from the March 2026 list of what is being demoted, and link presence is not among the post features LinkedIn describes feeding to its ranking model. LinkedIn has also never denied it. The third-party evidence is poor: the most-cited article presents no original data at all, and another widely-used source claims the opposite, that posts with several links do better, with no disclosed method.

What is real is the image-or-link tradeoff above. Decide on that basis, not on a rumour.

**Everything below: no evidence found in any LinkedIn source.**

- Optimal posting times
- Do not edit your post in the first hour
- The golden hour comment rule
- One-line "broetry" formatting increases reach
- Specific dwell-time-in-seconds targets
- Emoji are penalised
- LinkedIn now resurfaces posts that are two to three weeks old. This was a mid-2025 experiment that was rolled back, and guides still repeating it are stale.

**Not folklore, and worse than useless:** engagement pods and comment-automation extensions are explicitly against the rules and are being actively degraded.

---

## Where the third-party numbers come from

The larger studies, van der Blom's Algorithm Insights and AuthoredUp's dataset, are the best public data available and are still vendor research. Sample sizes are self-reported, methods are not independently published, and both organisations sell LinkedIn tools. Useful for direction, not for a decimal place.

## Staleness warning

LinkedIn's own help pages are unevenly maintained. The post character limit was updated within the last week; the media specification pages carry "last updated" dates two to three years old and may lag the product. The limits and the policy clauses have a long shelf life. Everything about ranking does not.
