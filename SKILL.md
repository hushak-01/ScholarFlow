---
name: scholar-flow
description: Orchestrate a repeatable, human-reviewed research workflow using Consensus for academic discovery, then Zotero and local LaTeX/TeXstudio for approved work. Use when onboarding a research profile, planning research tasks, searching and screening papers, asking the researcher to choose 精读/保存/忽略, organizing public literature knowledge and private research context, exporting BibTeX, drafting LaTeX, or diagnosing compilation errors.
---

# ScholarFlow

Turn available research tools into a human-reviewed, researcher-specific SOP from discovery to Zotero and LaTeX. ScholarFlow is the orchestration layer, not a replacement for academic databases or specialist tools. Prepare choices and evidence; leave novelty, correctness, relevance, and publication decisions to the researcher.

## Start

1. Locate the research workspace. If none exists, run `scripts/init_research_workspace.py <directory>`.
2. Read `private/research-profile.md` and `private/workflow-preferences.md`.
3. If required fields are missing, ask only unanswered questions from `references/onboarding.md`. Offer options plus “其他”. Do not repeat known answers.
4. Read `references/consensus.md` and `references/tool-routing.md`; verify whether the Consensus MCP is connected before literature discovery.
5. Default to Consensus for literature discovery and Zotero plus local TeXstudio for approved work.
6. Never commit or share files under `private/`.

## Route the request

- “今天做什么”：run the daily workflow.
- “找最近论文”：run discovery and screening.
- “精读这篇”：create a structured reading note.
- “保存到 Zotero”：validate, deduplicate, then save only approved items.
- “写/改 LaTeX”“编译报错”：run the LaTeX workflow.
- “更新研究方向”：update the private profile and preserve dated history.
- “有哪些工具可用”：report a capability matrix and gaps without installing or authorizing anything unless requested.

## Daily workflow

1. Use the profile, unfinished tasks, recent decisions, and available time to offer at most three tasks.
2. Read `references/consensus.md`, `references/tool-routing.md`, and `references/retrieval.md`. For literature discovery or evidence synthesis, call Consensus before general web or open-source search.
3. Deduplicate by DOI, then normalized title. Rank by topic, equation/problem, method, recency, seed-paper relationships, and exclusions.
4. Return 5 papers by default. Give title, authors, year, venue, DOI/link, short Chinese summary, relevance, access status, uncertainty, and `精读 / 保存 / 忽略` choices.
5. Stop for decisions. Never save all candidates automatically.
6. Apply decisions:
   - **精读**: separate claims, methods, assumptions, results, limitations, and connections. Never infer a proof from an abstract.
   - **保存**: follow `references/latex-zotero.md`; attach PDFs only when permitted.
   - **忽略**: record a short reason to tune future searches; do not make it permanent unless requested.
7. Update knowledge:
   - `literature-wiki/`: shareable, source-backed field knowledge.
   - `private/`: unpublished ideas, failed attempts, referee material, candid notes, decisions, and personal profile.
8. Cross-link private project notes to public literature pages without copying private content into them.

## Orchestration rules

- Use Consensus as the primary literature-discovery provider. A mention of Consensus in the prompt or documentation is not proof that it was called; invoke the connected Consensus tool and record the query.
- For discovery or evidence synthesis, run at least one focused Consensus search before supplementing with other sources. Use additional Consensus searches when distinct query families are needed; avoid wasting quota on duplicate queries.
- If Consensus is unavailable or unauthenticated, stop the discovery step, explain that the connection is missing, and give the official connection instructions from `references/consensus.md`. Offer the open-source retrieval path only as an explicit fallback choice.
- Route remaining tasks by capability. A tool is usable only if it is actually available and authorized in the current environment.
- Use specialist paper-reading tools for supplied or legally accessible full text when they improve the task; keep claims traceable to the paper.
- Use symbolic or numerical tools for computation checks, never as proof of theorem correctness.
- Keep one canonical candidate record across tools. Deduplicate results and preserve source, query, evidence level, uncertainty, and user decision.
- If Consensus returns an error after it was available, report the error and ask whether to retry or use the documented fallback. Never pretend a plugin was called.
- Do not install plugins, connect accounts, spend paid quota, or write to external libraries without the user's request or required authorization.

## LaTeX handoff

Read `references/latex-zotero.md`. Use Zotero as the bibliographic source of truth and a project `.bib` for TeXstudio. Inspect the project and build command, preserve classes/macros/labels/citation style, make the smallest scoped change, compile, diagnose the first meaningful error, and report unresolved warnings and claims requiring expert review.

Never silently rewrite proofs, change theorem assumptions, or replace citation keys across a project.

## Integrity, privacy, and optional IMA

- Label conjectures, proof sketches, and unverified citations.
- Require human review for correctness, novelty, authorship, submission, and final prose.
- Keep credentials in environment variables or an OS credential store, never in repository files.
- Do not scrape authenticated library pages, bypass limits, or redistribute licensed PDFs.
- Archive to IMA only when requested. Default to metadata, links, summaries, and user-authored notes; upload full text only when permitted.

## Finish

Append date, task, selected providers and fallbacks, queries, candidates, decisions, changed files, compile result, and next action to `private/run-log.md`. End with one recommended next step and at most three choices.

