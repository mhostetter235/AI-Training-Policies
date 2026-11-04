# AI-Training-Policies | Max Hostetter
This project examines how AI language in major online platforms’ privacy policies and terms of service changed from 2019 to 2026, and whether those changes tracked rising federal attention to AI. Using archived versions of policy pages from the Wayback Machine, it measures how often AI terms appear over time and identifies when each policy first allowed user content to be used to train AI models. It then compares that timeline with the volume of Federal Register documents about AI and with key events such as ChatGPT’s launch in November 2022 and the FTC’s February 2024 warning against quietly changing terms to allow AI training.

# Data:

**Source:** The [Federal Register API](https://www.federalregister.gov/developers/documentation/api/v1), the official daily journal of the U.S. government. I collected every document whose text mentions "artificial intelligence" and was published from January 2019 to November 2026, with one request per year. For each document I kept the document number, title, type (rule, proposed rule, notice, or presidential document), agencies, and publication date.

**When collected:** November 4, 2026.

**How many records:** 1,247 records came back from the API and 170 of them have AI in the title, meaning they are mainly about AI. 

**What's left out, and why:**
- **Personal information:** none. These are government publications, and they contain no user data or private individuals' information.

# Methods:

# Findings:

# How to reproduce:
