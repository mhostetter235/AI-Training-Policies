# Data dictionary

`federal_register_ai.csv`: one row per Federal Register document mentioning "artificial intelligence", 2019-2026.

| Field | Meaning |
|---|---|
| document_number | Unique Federal Register ID |
| title | Document title |
| type | Rule, Proposed Rule, Notice, or Presidential Document |
| agency_names | Issuing agencies, separated by semicolons |
| publication_date | Date published |
| about_ai | True if AI is in the title (document is mainly about AI) |
