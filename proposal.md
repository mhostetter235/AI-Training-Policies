
# Final Project Proposal: When Your Data Became Training Data

## 1. Research Question

How did AI language in major online platforms’ privacy policies and terms of service change from 2019 to 2026, and did those changes correlate with rising federal attention to AI?

**Who would care:** Privacy and consumer-protection advocates, lawyers, tech journalists, regulators, and users.

**What I expect:** Most platforms added training clauses in 2023 and 2024, after ChatGPT and before most federal activity.

**What would surprise me:** Training clauses well before 2022 or companies removing them later.

## 2. Data Sources and Method

### Source A: Company Policies, via the Wayback Machine

- **Endpoint:** The CDX API, https://web.archive.org/cdx/search/cdx, which lists saved snapshots of a URL. I fetch each snapshot's original page through `https://web.archive.org/web/{timestamp}id_/{url}` and extract its text with BeautifulSoup.
- **Scope:** About 35 privacy policy and terms pages from 17 companies.

### Source B: Federal AI Activity, via the Federal Register API

- **Endpoint:** https://www.federalregister.gov/api/v1/documents.json (free, no key).
- **Scope:** All documents from 2016 to October 2026 that mention "artificial intelligence," with title, agencies, type, date, and abstract. Many mention AI only in passing, so my main count keeps documents with AI in the title or abstract.

### Analysis

I will measure AI language in each policy version automatically, counting AI terms ("artificial intelligence," "machine learning," "train," "model") per 10,000 words so longer policies don't skew the results.

From that I will produce:

1. **A main chart:** Comparing the average AI language across platform policies per quarter with the number of Federal Register documents about AI per quarter.
2. **A "who moved first" comparison:** The quarter in which each line first reached half of its peak.
3. **Event windows:** The number of real policy changes in the six months before and after each event, to see whether changes clustered around them.
4. **Case studies:** Two or three policies read closely, with before-and-after excerpts showing what the new AI language allowed, plus OpenAI and Anthropic as a separate comparison group.

## 3. Ethics and Feasibility

### Terms of Service and robots.txt

- **Internet Archive:** Terms of Use allow access for research.
- **Federal Register:** U.S. government documents are public domain, and the API exists for reuse.
- **Company policies:** Public documents; I will quote only short excerpts for analysis, within fair use.
- **Limits:** A User-Agent with my name and CU email, pauses between Wayback requests (1 second for the Federal Register), and a local cache so no page is downloaded twice.

### Personal Information

None. Both sources are company and government documents.

### Fields I Will Use

From the Federal Register, I will use `document_number` to remove duplicates, `publication_date` to place documents on the timeline, and `title` and `abstract` to keep documents mainly about AI. I will also use `agency_name` to count activity by agency, including the FTC, and `html_url` if I need to cite specific documents.

### Biggest Risk and Fallback

The biggest risk is time and finding that there isn't much correlation between my two sources. My fallback is to start this project early so I can pivot if my findings are not sufficient.

