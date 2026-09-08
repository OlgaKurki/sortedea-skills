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


---

## Sources

**Employer platforms** were confirmed by following each employer's own application flow and reading the resulting hostname, CDN or page metadata, September 2026:
[Emirates Group](https://tas-ekgcareers.taleo.net/careersection/2/jobview.ftl) ·
[First Abu Dhabi Bank](https://www.bankfab.com/en-ae/about-fab/careers) ·
[Emirates NBD](https://www.emiratesnbd.com/en/careers) ·
[Etihad](https://careers.etihad.com/) ·
[Al-Futtaim](https://www.afuturewithus.com/) ·
[EY](https://careers.ey.com/) ·
[Deloitte Middle East](https://middleeastjobs.deloitte.com/careersME/) ·
[Chalhoub](https://careers.chalhoubgroup.com/locations/dubai) ·
[ADNOC](https://jobs.adnoc.ae/us/en) ·
[Majid Al Futtaim](https://careers.majidalfuttaim.com/) ·
[DEWA](https://www.dewa.gov.ae/en/about-us/the-workplace/careers)

Majid Al Futtaim's SuccessFactors HR core is separately evidenced by a [Rolling Arrays case study](https://rollingarrays.com/case-studies/majid-al-futtaim/), an SAP implementation partner. That confirms Employee Central, not the Recruiting module.

**Boards and regional ATS**
- [GulfTalent CV Search employer guide](https://www.gulftalent.com/employers/guides/cv-search). Boolean keyword search, nationality filter, no documented ranking
- [GulfTalent CV upload](https://www.gulftalent.com/job_application_upload_cv?job_id=337992). The 1MB cap
- [Bayt employer support](https://support.bayt.com/en/articles/6853478-do-a-cv-search). Silent on parsing
- [Naukrigulf CV Quality Score](https://www.naukrigulf.com/resume-services/cv-quality-score)
- [Talentera](https://www.talentera.com/en/). Client list is the vendor's own marketing

**Vendor documentation**
- [Oracle Taleo, attachments](https://docs.oracle.com/en/cloud/saas/taleo-enterprise/22d/otrcg/c-attachment.html)
- [Oracle Recruiting 25C release note](https://docs.oracle.com/en/cloud/saas/readiness/hcm/25c/recr-25c/25C-recruiting-wn-f38002.htm). Parsing via an unnamed third-party partner
- [Oracle Recruiting 25A, LinkedIn Apply Connect](https://docs.oracle.com/en/cloud/saas/readiness/hcm/25a/recr-25a/25A-recruiting-wn-f35389.htm)
- [Workday HiredScore, candidate profiles](https://doc.workday.com/hiredscore/en-us/workday-hiredscore/recruiter-productivity-/concept--candidate-profiles.html)
- [Greenhouse, supported formats](https://support.greenhouse.io/hc/en-us/articles/360052218132-Supported-formats-for-resumes-cover-letters-and-other-candidate-uploads) and [unsuccessful parse](https://support.greenhouse.io/hc/en-us/articles/200989175-Unsuccessful-resume-parse)
- [SmartRecruiters candidate support](https://candidatesupport.freshdesk.com/support/solutions/articles/9000026808-what-formats-can-i-use-for-my-resume-cv-or-cover-letter-)
- SAP SuccessFactors parsing limits could not be retrieved, the page is blocked to automated fetching. SAP KBA 2081576 is the authoritative source and needs a manual look.
