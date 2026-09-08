# The checks

Run these against the extracted text, not the visual layout. Everything here is either vendor-documented or mechanically obvious.

## Will break parsing

- **No text layer.** A scanned or image-exported PDF parses to nothing. Oracle's native path does not OCR ([Textkernel](https://www.textkernel.com/learn-support/blog/oracle-recruiting-cloud-resume-parsing/), vendor marketing but specific on this point).
- **Over the size limit.** [Greenhouse](https://support.greenhouse.io/hc/en-us/articles/360052218132-Supported-formats-for-resumes-cover-letters-and-other-candidate-uploads) stops parsing above 2.5MB. [GulfTalent](https://www.gulftalent.com/job_application_upload_cv?job_id=337992) rejects uploads above 1MB.
- **Contact details in the document header or footer.** Several parsers skip these regions. The result is a candidate with no phone number.
- **Multi-column layouts.** [Greenhouse](https://support.greenhouse.io/hc/en-us/articles/360052218132-Supported-formats-for-resumes-cover-letters-and-other-candidate-uploads) names columned layouts as a cause of failed parsing. Extract the text and check whether your two columns interleave into nonsense.
- **Complex tables.** Greenhouse names these too. A simple two-cell table usually survives; a nested one with merged cells does not.
- **Text boxes.** Content inside them may not be extracted at all.
- **Text as image.** Skills shown as a graphic, a logo containing your job title, a chart of competencies. None of it exists to a parser.
- **Unusual letter spacing.** [Greenhouse](https://support.greenhouse.io/hc/en-us/articles/360052218132-Supported-formats-for-resumes-cover-letters-and-other-candidate-uploads) lists spacing between letters as a parse-failure cause. Tracking applied for design can split words character by character in the extraction.

## Will read badly to a human

[The recruiter in Workday reads the parsed text](https://doc.workday.com/hiredscore/en-us/workday-hiredscore/recruiter-productivity-/concept--candidate-profiles.html), not your layout. So these matter even when parsing technically succeeds.

- **Non-standard section headings.** "Where I have made a difference" instead of "Experience". Parsers look for conventional headings and so do people skimming.
- **Inconsistent date formats.** Mixing `03/2021`, `Mar 2021` and `2021` across one document. [Workday computes employment gaps and time in position from these automatically](https://doc.workday.com/hiredscore/en-us/workday-hiredscore/recruiter-productivity-/concept--candidate-profiles.html).
- **Ambiguous dates.** `03/04/2022` is two different dates depending on where the reader is from.
- **Decorative bullet characters.** Custom icons and dingbats may extract as junk or vanish.
- **Acronyms with no expansion.** Give both once: "Applicant Tracking System (ATS)". Especially on GulfTalent, where search is literal and there is no semantic fallback.
- **A filename like `CV FINAL v3 (updated) copy.pdf`.** [SmartRecruiters](https://candidatesupport.freshdesk.com/support/solutions/articles/9000026808-what-formats-can-i-use-for-my-resume-cv-or-cover-letter-) advises short simple filenames with no spaces or special characters.
- **Tracked changes, comments or hidden revisions** left in a Word file.
- **Invisible page breaks** producing a blank page.

## Content and match

- **Does the CV use the words in the job advert?** Not stuffed, used. Where the advert says "stakeholder management" and the CV says "dealing with senior people", the words do not meet. This matters most on [GulfTalent](https://www.gulftalent.com/employers/guides/cv-search), where search is literal Boolean with no semantic fallback.
- **Are the employer's stated criteria addressed?** Years of experience, the specific qualification, the licence. This is what [the Harvard research](https://www.hbs.edu/managing-the-future-of-work/research/hidden-workers-untapped-talent) found people are actually filtered on.
- **Are gaps visible and unexplained?** They are computed automatically in some systems. Better to account for one in a line than to leave it as a hole.

## The application form

In Oracle and SAP deployments, recruiters filter on the structured form fields, not the CV text. Check separately:

- Every field completed, including the optional ones that are used as filters
- Form entries consistent with the CV, especially dates and job titles
- Knockout questions answered accurately. Visa status, licences and salary expectations are where genuine automatic rejection happens, far more than any keyword score

## Not a check

Do not flag font choice, a single simple table, use of PDF, the absence of a keyword density target, or a "score". None of these are evidenced. See `myths.md`.
