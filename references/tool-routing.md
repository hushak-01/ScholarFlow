# Tool routing and graceful fallback

ScholarFlow coordinates capabilities; it does not assume that any named plugin is installed. At the start of a run, inspect the tools available in the current environment and build a compact capability matrix.

| Capability | Preferred when available | Fallback | Human gate |
|---|---|---|---|
| Evidence search and synthesis | Connected academic search such as Consensus | arXiv, OpenAlex, Crossref, Semantic Scholar, publisher pages | Verify sources and relevance |
| Citation chaining and related work | Academic citation graph or research agent | References/citations on publisher pages and open indexes | Confirm relationship and scope |
| Full-text reading | Authorized full text plus a paper-reading tool | User-supplied PDF or legal open-access copy | Check theorem assumptions and page evidence |
| Symbolic or numerical checking | Wolfram or an available computation runtime | Local Python/Julia/MATLAB environment when available | Researcher validates mathematics |
| Reference management | Zotero | BibTeX/CSL JSON file prepared for review | Save only approved items |
| Writing and compilation | Project's existing LaTeX toolchain/TeXstudio | Produce a scoped `.tex` or patch without compiling | Review prose, claims, and authorship |
| Knowledge archive | `literature-wiki/`; optional IMA when requested | Local Markdown | Separate public and private context |

## Selection procedure

1. Identify the task and required capabilities.
2. Inspect what is connected, authorized, and suitable. Do not infer availability from a product name mentioned in documentation.
3. Select the smallest set of tools that covers the task. Explain the routing only when it affects the result or the user asks.
4. Normalize outputs into one candidate record with title, authors, year, venue, DOI/link, provider, exact query, evidence level, access status, relevance, uncertainty, and decision.
5. Deduplicate across providers by DOI, then normalized title.
6. Stop at the relevant human gate: `精读 / 保存 / 忽略`, mathematical verification, or final publication approval.
7. If a tool is unavailable or fails, use the next permitted fallback, log it, and state what became less certain or less complete.

## Provider boundaries

- Academic-search tools retrieve and synthesize evidence; they do not own the research profile or final judgment.
- Paper-reading tools explain accessible documents; they do not establish proof correctness.
- Computation tools test formulas and examples; numerical agreement is not a proof.
- Zotero is the bibliographic source of truth after approval, not a dumping ground for unreviewed candidates.
- ScholarFlow owns the SOP, state transitions, privacy split, audit trail, and handoffs between these components.
