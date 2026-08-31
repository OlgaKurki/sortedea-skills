# Sensitivity tiers — the sorting rules

Every fact in a playbook belongs to exactly one tier. When in doubt, sort upward (more protected), not downward.

## Tier 1 — Operating file (`playbook.md`)

**Test:** would you be comfortable if a trusted cover assistant read this while you were on leave?

Contains *how the principal works*, not *who they are*:

- Working hours, routine, energy patterns
- Meeting, scheduling and gatekeeping rules
- Communication preferences and voice
- Travel preferences (airline, seat, hotel, timing) — the preferences, not the numbers
- Named working relationships and how to handle each
- Food, drink and hospitality preferences
- Platforms and tools
- Confidentiality rules and emergency *procedure*
- Dietary requirements, stated as operational fact

This is the file AI assistants read. Keep it clean enough that handing it to one is an easy decision.

## Tier 2 — Private annex (`playbook-private.md`)

**Test:** would this identify, locate, or expose the principal or their family if the file leaked?

- Date of birth, passport and visa details, national ID
- Home and secondary addresses
- Family members, their names, schools, workplaces
- Personal contacts and their details
- Medical contacts, hospitals, insurance and assistance lines
- Loyalty programme numbers, corporate card details, payment routes
- Direct personal phone numbers

Hold this wherever your organisation holds confidential HR-grade material — the same standard as a personnel file. Do not paste it into AI tools, including this one. Do not email it. Do not keep it in a personal cloud account.

The operating file may reference the annex ("passport details: see annex"), never quote it.

## Tier 3 — Never recorded

- Passwords, passphrases, PINs
- 2FA backup codes, recovery keys
- API keys and tokens
- Answers to security questions
- Anything that authenticates as the principal

The right answer is a password manager with delegated emergency access. 1Password, Bitwarden and Keeper all support this properly: the principal keeps ownership, you get access under defined conditions, and the audit trail exists.

Record in the operating file only: which manager, who holds delegated access, and who to call if it fails.

### Why this is worth an argument

Being asked to keep a credential list is common, and refusing feels unhelpful. But that document outlives the relationship. It gets copied to a new laptop, emailed "just quickly", left in a Downloads folder, inherited by the next assistant. If it leaks, the assistant who typed it is the person the investigation starts with — and the harm to the principal is total, not partial.

Say it once, plainly, and offer the alternative: *"I won't keep a password list — if it ever leaked it'd be catastrophic for you and I'd be the one who wrote it. Let me set up delegated access in a password manager instead; you keep control and I can get in when you need me to."*

Almost nobody argues with that.

## Awkward middle cases

**Dietary requirements.** A preference ("doesn't eat red meat") is Tier 1 — a restaurant needs it. A medical condition ("coeliac", a named allergy with a severity) is health information: keep the operational instruction in Tier 1 in its plainest form ("strictly gluten-free, always flag to venues"), and any clinical detail in the annex.

**Family.** The *rule* is Tier 1 — "his wife's calls always go through, the kids' school is the only other number that interrupts a meeting." The *names, numbers and school* are Tier 2.

**Home address.** Tier 2, always, even for deliveries. The operating file can say "default delivery address is home — see annex."

**Birthday.** The date is Tier 2. A reminder to organise something in early March is Tier 1.

**Anything about the principal's health, finances, family difficulties, or personal life** that they told you in confidence and that does not change how you do your job: do not write it down at all. A playbook is an operating manual, not a file on a person. If recording it would embarrass them to read, it doesn't belong in either tier.

## The test that catches most mistakes

Before writing any line into the operating file, ask: *if this file were forwarded to the wrong person tomorrow, which lines would I regret?* Move those to the annex. If I'd regret them being in the annex too, don't write them.
