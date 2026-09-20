# Retrieval and screening

Use Consensus first according to `consensus.md`. When Consensus is unavailable or fails and the user explicitly chooses the open-source fallback, use this order:

1. arXiv, OpenAlex, Crossref, Semantic Scholar, and publisher open-access pages.
2. Authorized institutional APIs such as Web of Science, Scopus, and publisher APIs.
3. Links or PDFs supplied by the researcher.

Use official APIs, respect quotas and terms, and never assume campus web access includes automation or text-mining rights.

Construct narrow queries from equation/object, solution type/phenomenon, method, synonyms, variants, and date window. Retain exact queries. For each candidate record source, retrieval date, ID/link, matched terms, evidence level, relevance, access status, and user decision. Do not use citation count alone as a quality score.

When a connected provider performs search, synthesis, or citation chaining, record the provider and preserve links to the underlying papers. Treat generated summaries as navigation aids, not as verified theorem statements. Merge and deduplicate candidates before presenting them to the researcher.

