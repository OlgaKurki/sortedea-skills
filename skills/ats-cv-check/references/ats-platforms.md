# Who runs what

Checked September 2026 by reading the employers' own application flows. Careers pages get replatformed, so re-check before relying on a row.

## UAE employers, confirmed

| Employer | System | How it was confirmed |
|---|---|---|
| Emirates Group (Emirates, dnata) | **Oracle Taleo** | Applications resolve to `tas-ekgcareers.taleo.net` |
| First Abu Dhabi Bank | **Oracle Fusion / HCM Cloud** | `fa.em2.oraclecloud.com/hcmUI/CandidateExperience` |
| Emirates NBD | **Oracle Fusion / HCM Cloud** | `fa.ocs.oraclecloud.com/hcmUI/CandidateExperience` |
| Etihad Airways | **SmartRecruiters** | `careers.smartrecruiters.com/EtihadAirways5` |
| Al-Futtaim Group | **SAP SuccessFactors** | Career site served from `rmkcdn.successfactors.com` |
| EY (incl. MENA) | **SAP SuccessFactors** | Site states it "is based on the SuccessFactors software provided by SAP" |
| Deloitte Middle East | **Avature** | Portal meta tags name Avature |
| Chalhoub Group | **Teamtailor** | "Career site by Teamtailor" in the footer |
| ADNOC | **Phenom** front end | `cdn.phenompeople.com`. Underlying ATS not confirmed |
| Majid Al Futtaim | **Phenom** front end | `cdn.phenompeople.com`. SuccessFactors confirmed for HR core, not for recruiting |
| DEWA | In-house government portal | No third-party vendor markers |

**The pattern.** The UAE market is Oracle and SAP. Both are enterprise HR suites where recruiting is bolted onto the HR core, which means conservative parsing and long structured application forms.

**Phenom and Teamtailor are front ends.** What the candidate sees is often not the system storing the parsed CV. Do not assume the visible brand is the parser.

**Workday was not confirmed at any UAE employer checked.** Plausible at multinationals, unverified. So testing "against Workday as the worst case", which most guides recommend, is aimed at the wrong system for this market. Test against Taleo and Oracle Fusion.

**Not checked, unknown:** Mashreq, Mubadala, Dubai Holding, Landmark, PwC and KPMG in the region, and UAE healthcare groups.

## Job boards are not ATSs

Bayt, GulfTalent, Naukrigulf and Qureos are job boards. **Talentera** is the ATS spun out of Bayt, and it is regionally real: its own client list names RAKBANK, GEMS, Dubai Islamic Bank, Royal Jet, the UAE Ministry of Economy and Dubai Future Foundation.

**GulfTalent is literal keyword search, not matching.** Its own employer guide describes keyword search across the CV text with Boolean operators, and documents no ranking or scoring. So on GulfTalent your exact word choice matters more than anywhere else, because there is no semantic fallback. If the recruiter searches "executive assistant" and you wrote "EA", you are not in the results.

**GulfTalent lets employers filter on nationality**, alongside keywords, function and location. That is documented in the same guide.

**GulfTalent caps uploads at 1MB**, Word or PDF. This is the tightest limit found anywhere and a photo-heavy CV will breach it.

**Bayt publishes nothing** about how it parses or indexes. Do not make claims about it.

**Naukrigulf sells a "CV Quality Score"** on undisclosed parameters. It is a commercial product, not evidence about ATS behaviour.

## What the vendors themselves document

**Every vendor checked accepts PDF.** "ATSs cannot read PDFs" is false.

| Vendor | Formats | Limits worth knowing |
|---|---|---|
| Oracle Taleo | PDF, DOC, DOCX, RTF, TXT, HTML, ODT and more; the administrator chooses which are enabled | Enabled set varies by employer |
| Oracle Fusion Recruiting | Parsing runs through an unnamed third-party partner integration | Oracle does not publish formats or accuracy limits |
| SAP SuccessFactors | Not retrievable, blocked to automated fetching | Check SAP KBA 2081576 manually |
| Workday (HiredScore) | DOC, DOCX, PDF, RTF, TXT | **Computes employment gaps and time in position automatically.** Recruiters read the parsed text, not your layout |
| Greenhouse | DOC, DOCX, PDF, RTF, TXT | **Parsing stops above 2.5MB.** Lists the causes of failure as letter spacing, graphics, columned layouts, complex tables and unclear section formatting |
| SmartRecruiters | DOC, DOCX, RTF, PDF, TXT | Advises short simple filenames with no spaces or special characters |

**Greenhouse also documents what happens on failure:** the recruiter enters the details manually and the CV remains attached. Worth quoting to anyone who believes a formatting slip is fatal.

**Scanned PDFs are the real format risk.** Oracle's native path does not OCR. A CV that is an image of a CV parses to nothing.
