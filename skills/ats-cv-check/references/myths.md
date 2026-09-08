# What not to repeat

The ATS advice industry runs on numbers nobody can source. Repeating them makes the rest of the advice less trustworthy.

## "75% of CVs are rejected by ATS before a human sees them"

**A myth with a traceable origin.** The figure comes from **Preptel**, a CV-optimisation vendor, in 2012. Preptel ceased operations in 2013. It never published a study, a methodology or a sample size. The provenance is traced in [JobCannon's write-up](https://jobcannon.io/research/stats/ats-myth-preptel). Every version of the claim circulating since is a repetition of a defunct vendor's sales pitch.

Say so if someone quotes it. It is more useful than a hedge.

## "The ATS auto-rejects you"

Mostly false, and it is a configuration choice rather than a property of the software.

The nearest available data is an [Enhancv survey](https://enhancv.com/blog/does-ats-reject-resumes/) of **25 US recruiters** across more than ten platforms: 92% said their system does not auto-reject on formatting, design, missing keywords or match score. 44% had fit scores available and most had disabled them or treated them as advisory. One quote from it: *"ATS systems don't automatically disposition people, we have to go in and do it ourselves."* Also covered by [ITBrief](https://itbrief.co.uk/story/study-reveals-ats-rarely-auto-rejects-cvs-debunks-75-myth).

**Caveat it properly.** Twenty-five recruiters, US only, run by a CV vendor, self-reported. It refutes the 75% claim. It does not establish 92% as a fact.

Where genuine automatic rejection does happen is **knockout questions**: visa status, a required licence, a minimum salary. Those are answered on the form, not written on the CV.

## "It's the formatting that's stopping you"

The largest real study points elsewhere. [Hidden Workers: Untapped Talent](https://www.hbs.edu/managing-the-future-of-work/research/hidden-workers-untapped-talent), Harvard Business School and Accenture, 2021.

Verbatim from the report: *"We surveyed 2,275 executives, reaching out to a minimum of 750 executives in each of these three countries: the United States, the United Kingdom, and Germany"*, fielded January to February 2020. *"More than 90% of employers in our survey use their RMS to initially filter or rank potential middle-skills (94%) and high-skills (92%) candidates."* And: *"A large majority (88%) of employers agree, telling us that qualified high-skills candidates are vetted out of the process because they do not match the exact criteria established by the job description. That number rose to 94% in the case of middle-skills workers."*

The figure is often cited elsewhere as "more than 2,250 executives". 2,275 is the number printed in the report.

That is about **employer-configured criteria**: years of experience, a specific degree, an unbroken work history. It is not about fonts, tables or templates. A cleaner CV does not address it. Meeting or explicitly addressing the stated criteria does.

This distinction is the single most useful thing to tell someone who is not hearing back.

## "PDFs cannot be read"

False. [Oracle Taleo](https://docs.oracle.com/en/cloud/saas/taleo-enterprise/22d/otrcg/c-attachment.html), [Workday HiredScore](https://doc.workday.com/hiredscore/en-us/workday-hiredscore/recruiter-productivity-/concept--candidate-profiles.html), [Greenhouse](https://support.greenhouse.io/hc/en-us/articles/360052218132-Supported-formats-for-resumes-cover-letters-and-other-candidate-uploads) and [SmartRecruiters](https://candidatesupport.freshdesk.com/support/solutions/articles/9000026808-what-formats-can-i-use-for-my-resume-cv-or-cover-letter-) all list PDF as supported.

The real format risks are specific: a **scanned or image PDF with no text layer** ([Textkernel sells OCR precisely because Oracle's native path lacks it](https://www.textkernel.com/learn-support/blog/oracle-recruiting-cloud-resume-parsing/)), a file **over the size limit**, and **right-to-left text**, which is documented as broken in the extraction libraries parsers are built on: [PyMuPDF #2199](https://github.com/pymupdf/PyMuPDF/issues/2199), [docling #1938](https://github.com/docling-project/docling/issues/1938), [markitdown #2336](https://github.com/microsoft/markitdown/issues/2336).

## "Never use tables"

Overstated. [Greenhouse's own documentation](https://support.greenhouse.io/hc/en-us/articles/360052218132-Supported-formats-for-resumes-cover-letters-and-other-candidate-uploads) names **complex tables** and **columned layouts** as causes of parse failure. A simple table is usually fine. And [a parse failure means a recruiter types your details in by hand](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse), not that you are eliminated.

## "Keyword density should be X%"

Invented. No vendor publishes a density target and none of the available parsing documentation scores by frequency. Any specific number is made up.

## "White text keyword stuffing works" and "ATSs detect and blacklist it"

Both unevidenced, and the practice is a bad idea for a reason neither claim captures.

Parsers read the text layer, so hidden white text **is** ingested. But recruiters read the parsed text too. [Workday presents candidates' parsed CVs to recruiters](https://doc.workday.com/hiredscore/en-us/workday-hiredscore/recruiter-productivity-/concept--candidate-profiles.html), and colour does not exist in extracted text. So it is plainly visible to the person you are trying to fool.

Say that. Do not claim systems detect and blacklist it, because no vendor documents that.

## "Your CV gets a match score that decides your fate"

Half true. Scores exist. The evidence is that they are advisory and frequently switched off, and that a human dispositions the candidate.

## The general rule

When there is no evidence, say there is no evidence. "Nobody has published data on this, but here is the mechanical reason it is a bad idea" is more useful, and more credible, than a confident number.


---

## Every source on this page

- [Hidden Workers: Untapped Talent](https://www.hbs.edu/managing-the-future-of-work/research/hidden-workers-untapped-talent). Harvard Business School / Accenture, 2021. Primary source, PDF
- [JobCannon on the Preptel origin of the 75% figure](https://jobcannon.io/research/stats/ats-myth-preptel)
- [Enhancv, does the ATS reject your resume](https://enhancv.com/blog/does-ats-reject-resumes/). The n=25 recruiter survey
- [ITBrief coverage of the same study](https://itbrief.co.uk/story/study-reveals-ats-rarely-auto-rejects-cvs-debunks-75-myth)
- [Greenhouse, supported formats](https://support.greenhouse.io/hc/en-us/articles/360052218132-Supported-formats-for-resumes-cover-letters-and-other-candidate-uploads)
- [Greenhouse, unsuccessful resume parse](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse)
- [Workday HiredScore, candidate profiles](https://doc.workday.com/hiredscore/en-us/workday-hiredscore/recruiter-productivity-/concept--candidate-profiles.html)
- [Oracle Taleo, attachments and supported formats](https://docs.oracle.com/en/cloud/saas/taleo-enterprise/22d/otrcg/c-attachment.html)
- [SmartRecruiters, accepted CV formats](https://candidatesupport.freshdesk.com/support/solutions/articles/9000026808-what-formats-can-i-use-for-my-resume-cv-or-cover-letter-)
- [Textkernel on Oracle Recruiting Cloud parsing](https://www.textkernel.com/learn-support/blog/oracle-recruiting-cloud-resume-parsing/). Vendor marketing, discount accordingly
- RTL extraction bugs: [PyMuPDF #2199](https://github.com/pymupdf/PyMuPDF/issues/2199), [docling #1938](https://github.com/docling-project/docling/issues/1938), [markitdown #2336](https://github.com/microsoft/markitdown/issues/2336)

Checked September 2026.
