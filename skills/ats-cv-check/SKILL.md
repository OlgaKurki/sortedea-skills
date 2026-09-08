---
name: ats-cv-check
description: Check a CV against the applicant tracking systems that will actually parse it, then rebuild it clean. UAE-first, covering Oracle Taleo, Oracle Fusion, SuccessFactors and the regional boards.
---

# ATS CV check

**Use this skill when** someone wants their CV checked for ATS problems, asks whether their CV will get through, is applying for a job in the UAE or Gulf, or asks to make a CV ATS compliant. Phrases that mean this skill: "ATS check", "will my CV parse", "is my CV ATS friendly", "make my CV ATS compliant", "why am I not hearing back", "check my resume".

Most ATS advice is written for the American market and tells you to fear Workday. In the UAE, the systems that will actually read your CV are **Oracle and SAP**, and the highest-leverage fix is usually not the CV at all. Get that right before anything else.

## Start honestly

Before the first check, say this plainly, because it changes what the person should spend their effort on:

**A parsing failure does not reject you.** [Greenhouse documents](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse) that when a CV fails to parse, the recruiter enters the details by hand and the CV stays attached to your profile. Bad formatting creates friction and a worse first impression. It is not a trapdoor.

**The "75% of CVs are rejected by ATS" figure is a myth.** It traces to Preptel, a CV-optimisation vendor, in 2012. Preptel shut down in 2013 and never published a study behind the number ([provenance](https://jobcannon.io/research/stats/ats-myth-preptel)). Anyone quoting it is quoting a sales pitch.

**What genuinely filters people out is the employer's own criteria**, not your font. Harvard Business School and Accenture [surveyed 2,275 executives](https://www.hbs.edu/managing-the-future-of-work/Documents/research/hiddenworkers09032021.pdf) and found 88% agreed qualified high-skills candidates were vetted out for not matching the exact criteria in the job description, rising to 94% for middle-skills roles. That is years of experience, a specific degree, an unbroken work history. A cleaner template does not touch it. Matching or addressing the stated criteria does.

So: fix the formatting because it is cheap and it helps a human read you. Do not believe it is the reason you are not hearing back.

## Step 1. Find out what you are up against

Ask two questions:

1. **Which employer, or which job?** This decides the platform. `references/ats-platforms.md` maps the major UAE employers to their actual systems.
2. **How are you applying?** Company careers page, a regional board (Bayt, GulfTalent, Naukrigulf), or LinkedIn Easy Apply. These behave differently, and Easy Apply may send your LinkedIn profile rather than the CV you tailored.

If they do not know the employer, default to **Oracle Taleo and Oracle Fusion** as the test target for the UAE. That is what Emirates, FAB and Emirates NBD run.

**The thing most guides miss.** Oracle and SAP deployments put a long structured application form in front of you, and in those systems recruiters filter on the form fields, not on your CV text. A perfect CV behind a half-filled form still loses. Tell the person to complete every field and keep it consistent with the CV, and treat that as a higher priority than any formatting fix.

## Step 2. Read the file as the parser would

Get the actual file, not a description of it. Then check:

- **Is there a text layer?** If the PDF is a scan or an exported image, there is no text to parse and nothing else matters. Oracle's native path does not OCR. Fix: export a real PDF from the source document.
- **What comes out when you extract the text?** Read that extraction, not the visual layout. Reading order, lost content and merged columns all show up here and nowhere else.
- **File size.** Greenhouse stops parsing above 2.5MB. GulfTalent rejects uploads above 1MB outright, which a photo-heavy CV will breach.
- **Filename.** SmartRecruiters advises short, simple filenames without spaces or special characters. `firstname-lastname-cv.pdf`, not `CV FINAL v3 (updated) copy.pdf`.

Then run the structural checks in `references/checks.md`.

## Step 3. Report

Use this structure. Order by what actually costs them something.

```
# ATS check: [filename]

**Applying to:** [employer] via [platform]
**Verdict:** [one sentence]

## Will break parsing
[Issue] · [where] · [fix]

## Will read badly to a human
[Issue] · [where] · [fix]

## UAE content decisions
[What to add, remove or reconsider for this market]

## Worth doing
[Lower priority]

## Working well
[Genuine strengths, not filler]

## The bigger lever
[What matters more than formatting for this application]
```

Be specific about location. "Your contact details are in the document header, which several parsers skip entirely. Result: you appear to have no phone number." Not "check your contact details".

Give a verdict, not a score out of ten. A number invites people to optimise for the number, and no ATS publishes one you could be scoring against.

## Step 4. Offer to rebuild

Once they have seen the report, offer to produce a clean version. Do not do it unasked, and do not do it instead of the report.

Rebuild to the structure in `assets/ats-safe-structure.md`. Output **.docx** unless they ask otherwise: it is universally supported, it is editable, and it removes the scanned-PDF risk entirely.

**The rule that matters more than any formatting rule:**

> Never add a skill, a tool, a qualification, a date or a responsibility the person did not tell you they have. Not to match a job description, not to improve keyword coverage, not because it is probably true.

Rewriting phrasing is help. Adding content is writing a false document that they will have to defend in an interview and that may cost them a visa. If a job description wants something they lack, say so and let them decide.

Two related limits:

- **No white text, no hidden keywords, no invisible stuffing.** Parsers read the text layer, so hidden text is ingested. But recruiters in Workday read the parsed text too, where colour does not exist, so it is visible to them as well. It is a detection risk with no proven benefit.
- **Keep every date, employer name and title exactly as given.** Workday's HiredScore computes employment gaps automatically from your dates. Do not tidy a gap away by stretching a date.

After rebuilding, tell them what you changed and what you removed, in a short list.

## The UAE content questions

These are decisions about what goes on the CV, not formatting, and they are where this market genuinely differs. The detail and the sourcing are in `references/uae-cv-conventions.md`. In short:

| | |
|---|---|
| **Nationality** | Expected in practice. Also legally uncomfortable, see below |
| **Visa status** | Expected. Employers price transfer against a new permit |
| **Photograph** | Genuinely contested. Do not state a rule |
| **Current salary** | Leave out |
| **Religion** | Leave out |
| **Emirates ID number** | Never on a CV |
| **Languages with proficiency** | Include. Arabic and English is a real differentiator |
| **Length** | Two pages, three at the outside |

**Say the legal tension out loud rather than presenting nationality as neutral best practice.** UAE Federal Decree-Law 33 of 2021 prohibits discrimination on national origin and covers recruitment. Nationality is nonetheless a standard CV field and a live search filter on GulfTalent. Both things are true. Give the person the facts and let them choose.

**Bilingual CVs.** Submit English only to the ATS. Right-to-left text extraction from PDFs is genuinely broken across the libraries parsers are built on, so Arabic can come out reversed or scrambled. Offer the Arabic version as a separate document if asked. This is about the PDF toolchain, not about Arabic names: there is no evidence that transliterated names break parsers, so do not claim there is.

## What not to say

`references/myths.md` covers the claims to avoid repeating. The short list: no percentage of CVs auto-rejected, no keyword density target, no "ATS blacklists you for hidden text", no "PDF is unreadable", no claim that a particular font or a single table will get you binned. When the honest answer is that nobody has published evidence, say that.
