# UAE CV conventions

What differs from a US or UK CV, with the evidence, and flagged where the sources disagree.

## The honest state of each field

| Field | Verdict | Evidence |
|---|---|---|
| **Nationality** | Expected in practice | Bayt calls it a standard UAE expectation. Corroborated by GulfTalent offering it as an employer search filter |
| **Visa status and type** | Expected | Bayt advises stating resident, visit visa or overseas applicant. The rationale is real: a transfer costs an employer less than a new permit |
| **Photograph** | **Contested. Do not state a rule** | Bayt recommends a professional headshot. Michael Page UAE says the opposite, that photographs are not necessary. Both are credible regional sources and they disagree |
| **Current salary** | Leave out | Michael Page states it should not be included |
| **Expected salary** | No evidence either way | Ask the person, do not rule |
| **Notice period** | Useful, unevidenced | No credible source found recommending it. Relevance is real under UAE notice law, but "put it on the CV" is not documented |
| **Marital status** | Optional, trending out | Bayt itself says not required, include only if relevant |
| **Date of birth** | Optional | Bayt calls it optional but common. Note age is not a protected characteristic under the UAE statute below, which is why the practice survives |
| **Religion** | Leave out | Michael Page explicitly warns against it. Also a protected characteristic |
| **Emirates ID number** | **Never** | No source recommends it. It is a national identity number on a document circulated to strangers, with no upside. This is judgement, not a sourced finding |
| **Languages with proficiency** | Include | Bayt advises listing each language with level. Arabic and English together is a genuine regional differentiator |
| **Driving licence** | Role dependent | Relevant for field, sales and logistics roles |
| **References** | "Available on request" | Bayt and Michael Page agree, which is rare |
| **Length** | Two pages, three maximum | Michael Page |

## The legal tension, which should be said out loud

UAE Federal Decree-Law 33 of 2021, Article 4, prohibits discrimination on race, colour, sex, religion, national origin, social origin and disability, and the protection covers recruitment.

Nationality falls under national origin. It is also a standard CV field in this market and a live employer search filter on GulfTalent.

Both of those are true at once. The useful thing to do is give the person the facts and let them decide, rather than presenting nationality as neutral best practice or pretending the norm does not exist.

**Age is not in the protected list**, which is the practical reason date-of-birth requests persist here in a way they would not in the UK.

## Bilingual and Arabic

**Submit English only to the ATS.** Right-to-left text extraction from PDFs is documented as broken across the open-source libraries that parsers are built on: reversed characters, corrupted ligatures, lost reading order. These are open issues in PyMuPDF, docling and markitdown, and long-running threads in Adobe's own community. The bug class is real. Whether a specific ATS exhibits it is unverified, which is reason enough not to find out with a live application.

Offer the Arabic version as a separate attachment if the employer asks for one.

**Do not claim transliterated names break parsers.** The advice about Al- versus Al versus El-, bin, and Abdul hyphenation is repeated everywhere and evidenced nowhere. What is defensible without invoking the parser: spell your name identically across your CV, LinkedIn and passport, because humans and identity checks both rely on it.

**Hijri dates.** No evidence exists about ATS handling. Gregorian is standard on UAE CVs anyway. Do not invent a rule.

## Attestation and MOHRE skill levels

MOHRE classifies occupations into nine skill levels. Levels one to three require a diploma or degree, and for skilled occupations the qualification may need attesting by the competent authorities.

**Attestation is a post-offer process, not a screening step**, so it does not belong as a CV section. If a degree is already attested or equivalency is obtained, one line in the covering note is defensible because it removes a known delay from the employer's onboarding. No source recommends this. Present it as reasoning, not as practice.

Cite the live u.ae and Ministry of Education pages if the person needs the process itself. The search results for attestation are dominated by agencies selling the service.


---

## Sources

- [Bayt, CV format for UAE jobs](https://www.bayt.com/en/blog/32538/cv-format-for-uae-jobs-the-complete-2026-guide/). Regional job board, so read the photograph advice with that in mind
- [Michael Page UAE, how to write a great CV](https://www.michaelpage.ae/advice/career-advice/cover-letter-and-cv-advice/how-write-great-cv). International recruiter, and the source that disagrees with Bayt on photographs
- [GulfTalent CV Search employer guide](https://www.gulftalent.com/employers/guides/cv-search). Documents nationality as an employer search filter
- [Chambers, UAE labour laws and discrimination](https://chambers.com/articles/uae-labour-laws-safeguarding-employees-from-discrimination). Federal Decree-Law 33 of 2021, Article 4, and its application to recruitment
- [Gulf News on MOHRE skill levels](https://gulfnews.com/living-in-uae/ask-us/uae-mohre-skill-levels-explained-how-they-affect-jobs-visas-and-salaries-1.500666331). The nine-level classification and attestation
- RTL extraction bugs: [PyMuPDF #2199](https://github.com/pymupdf/PyMuPDF/issues/2199), [docling #1938](https://github.com/docling-project/docling/issues/1938), [markitdown #2336](https://github.com/microsoft/markitdown/issues/2336)

For attestation itself, cite the live [u.ae](https://u.ae/) and Ministry of Education pages rather than the agency sites that dominate search for that term.

Checked September 2026.
