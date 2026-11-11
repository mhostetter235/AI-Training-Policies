# AI-Training-Policies | Max Hostetter
This project examines how AI language in major online platforms’ privacy policies and terms of service changed from 2019 to 2026, and whether those changes tracked rising federal attention to AI. Using archived versions of policy pages from the Wayback Machine, it measures how often AI terms appear over time and identifies when each policy first allowed user content to be used to train AI models. It then compares that timeline with the volume of Federal Register documents about AI and with key events such as ChatGPT’s launch in November 2022 and the FTC’s February 2024 warning against quietly changing terms to allow AI training.

# Data:

**Source:** The [Federal Register API](https://www.federalregister.gov/developers/documentation/api/v1), the official daily journal of the U.S. government. I collected every document whose text mentions "artificial intelligence" and was published from January 2019 to November 2026, with one request per year. For each document I kept the document number, title, type (rule, proposed rule, notice, or presidential document), agencies, and publication date.

**When collected:** November 4, 2026.

**How many records:** 1,247 records came back from the API and 170 of them have AI in the title, meaning they are mainly about AI. 

**What's left out, and why:**
- **Personal information:** none. These are government publications, and they contain no user data or private individuals' information.

# Methods:

Federal Register documents were collected via the Federal Register API, querying for the term “artificial intelligence” across each year from 2019 to 2026. Each request retrieved up to 1,000 documents per year, capturing document number, title, type, agency names, and publication date. Raw JSON responses were saved locally and deduplicated by document number, yielding 1,247 unique records. Documents were then flagged as primarily about AI if their title contained “artificial intelligence” or the standalone term “AI".

# Findings:

A Federal Register API query for documents mentioning “artificial intelligence” (2019–2026) returned 1,247 unique documents, 170 of which are primarily about AI. Federal attention was minimal through 2020, rose sharply after 2022, coinciding with the mainstreaming of generative AI, and peaked in 2024 before tapering off toward pre-ChatGPT levels.

# How to reproduce:
