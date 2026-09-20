# ScholarFlow · 研流

[简体中文](#简体中文) · [English](#english) · [日本語](#日本語) · [한국어](#한국어)

## 简体中文

ScholarFlow 是一套面向高校教师、研究生与科研团队的人工审核型 AI 科研工作流。它不是另一个论文数据库，而是一个可组合现有科研插件与工具的编排层：先识别当前可用能力，再根据研究者画像连接论文检索与筛选、Zotero 归档、知识沉淀和本地 TeXstudio/LaTeX 写作。

```text
科研画像 → 能力盘点 → 按任务调用 Consensus / 开放论文源 / 计算工具
        → 论文雷达 → 精读 / 保存 / 忽略
        → Zotero → BibTeX → TeXstudio / LaTeX
        → literature-wiki（公开）+ research-profile（私有）
```

默认每周筛选5篇论文，并在保存前交给研究者判断。IMA可以作为可选知识归档端。

安装了 Consensus 等学术检索工具时，ScholarFlow 可以优先利用其证据检索、综合和引用追踪能力；未安装时会回退到 arXiv、OpenAlex、Crossref、Semantic Scholar 和出版社页面。任何单一插件都不是运行前提。

快速开始：对助手说 `使用 $scholar-flow 开始我的科研工作流。`

### 知识分层

- `literature-wiki/`：可分享的领域知识。
- `private/`：研究画像、未发表想法、失败尝试及审稿材料，不得提交到公开仓库。

### 安全边界

不要提交 API Key、学校账号或私人研究资料；不要绕过付费墙或传播授权受限的论文全文；AI生成的证明、引文和学术判断必须由研究者核验。

## English

ScholarFlow is a plugin-aware, human-in-the-loop orchestration workflow connecting available academic tools, literature discovery, paper screening, Zotero, knowledge accumulation, and local TeXstudio/LaTeX. It uses connected research tools when available and degrades gracefully to open sources. It separates shareable field knowledge from strictly private research context. Researchers retain final authority over correctness, novelty, citations, authorship, and publication.

Start with: `Use $scholar-flow to start my research workflow.`

## 日本語

ScholarFlow は、論文検索、Zotero、知識整理、ローカルの TeXstudio/LaTeX をつなぐ研究支援ワークフローです。AIが候補と根拠を整理し、研究者が「精読・保存・除外」を判断します。公開知識と非公開研究情報を明確に分離します。

## 한국어

ScholarFlow는 논문 탐색, Zotero, 지식 축적, 로컬 TeXstudio/LaTeX를 연결하는 연구 워크플로입니다. AI는 후보와 근거를 준비하고, 연구자는 정독·저장·제외를 결정합니다. 공개 지식과 비공개 연구 맥락을 분리합니다.

## Inspirations

- [research_LLM_wiki](https://github.com/jinleiphys/research_LLM_wiki): literature wiki and private research profile.
- [ai-research-skills](https://github.com/WenyuChiou/ai-research-skills): resumable state and human review gates.
- [ResearchClaw](https://github.com/ymx10086/ResearchClaw): literature discovery workflow patterns.

Independent implementation; workflow ideas are referenced rather than upstream source code being copied.

## Status

Version 0.2 adds capability discovery, plugin-aware task routing, cross-provider deduplication, and graceful fallback while preserving the research profile, human review gates, privacy rules, Zotero/LaTeX handoff, and non-destructive workspace initializer. Direct Zotero API writing and scheduled retrieval are planned.

## License

MIT
