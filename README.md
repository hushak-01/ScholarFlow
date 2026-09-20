# ScholarFlow · 研流

> 让 AI 不只是回答一个问题，而是陪你按固定流程持续做科研。

[简体中文](#简体中文) · [English](#english) · [日本語](#日本語) · [한국어](#한국어)

## 简体中文

### 它解决什么问题？

科研人员已经可以用 Consensus 查文献、用 Zotero 管论文、用 Wolfram 或 Python 做计算、用 LaTeX 写文章。

真正麻烦的是：**工具很多，但每次仍要重新解释研究方向、决定今天做什么，并手动把检索、筛选、精读、归档和写作串起来。**

ScholarFlow 是一个可安装到 Codex 的科研工作流 Skill。它会先了解研究者，再根据当前可用的插件和工具组织每天或每周的科研任务。

### 它会怎么工作？

```text
第一次使用
  → 建立你的科研画像：方向、关键词、重要作者、期刊和排除项

每次运行
  → 检查当前有哪些科研插件和工具可用
  → 根据画像规划今天或本周的任务
  → 调用合适的工具检索和筛选论文
  → 让你选择：精读 / 保存 / 忽略
  → 经你确认后进入 Zotero、知识库或 LaTeX 项目
  → 记录你的判断，让下一次筛选更贴近你的需要
```

默认示例是：**每周筛选 5 篇论文，由研究者做最终判断。**

### 它和 Consensus 有什么区别？

| 工具 | 主要职责 |
|---|---|
| Consensus 等科研插件 | 查论文、找证据、追踪引用和生成文献综述 |
| Zotero | 管理已经确认需要保存的文献 |
| Wolfram / Python | 辅助公式、符号和数值计算 |
| TeXstudio / LaTeX | 写作与编译论文 |
| **ScholarFlow** | 了解研究者，并把以上工具组合成一套可重复的科研 SOP |

ScholarFlow 不会重复造一个论文数据库。检测到 Consensus 等工具时，它会优先使用；没有这些插件时，会回退到 arXiv、OpenAlex、Crossref、Semantic Scholar 和出版社公开页面。

### 为什么还要让研究者做选择？

AI 可以减少查找和整理时间，但不能替代研究者判断：

- 论文是否真的相关；
- 定理条件和证明是否正确；
- 结果是否具有新意；
- 是否应该引用、保存或用于投稿。

因此，ScholarFlow 不会把检索到的论文全部塞进 Zotero，也不会把 AI 生成的证明直接当作正确结论。

### 快速开始

在 Codex 中新建一个任务，然后发送：

```text
请从 https://github.com/hushak-01/ScholarFlow 安装 ScholarFlow Skill。
```

安装完成后，打开一个新的 Codex 任务，发送：

```text
使用 $scholar-flow 开始我的科研工作流。
先了解我的研究方向，再检查当前可用的科研插件和工具。
```

你也可以直接开始一次论文雷达：

```text
使用 $scholar-flow，根据我的科研画像检索本周最值得关注的5篇论文，
让我逐篇选择：精读、保存或忽略。未经确认，不要写入 Zotero。
```

### 知识如何保存？

- `literature-wiki/`：有文献依据、可以分享的领域知识。
- `private/`：个人科研画像、未发表想法、失败尝试、审稿材料和运行记录。

`private/` 默认只保存在本地，不应提交到公开 GitHub 仓库。IMA 可以作为可选的知识归档端，但不是运行 ScholarFlow 的必要条件。

### 当前版本

v0.2 已支持：

- 不同研究者的科研画像；
- 可用插件与工具盘点；
- 按能力选择工具，而不是绑定单一品牌；
- 插件不可用时自动降级到开放论文源；
- 跨来源去重与检索记录；
- `精读 / 保存 / 忽略` 人工审核；
- Zotero、BibTeX 与本地 TeXstudio/LaTeX 衔接；
- 公开知识与私人研究信息分离。

后续计划：更方便的 Zotero 写入、定时论文雷达和真实科研场景下的持续调优。

### 安全与学术边界

- 不要把 API Key、学校账号或私人研究资料提交到公开仓库。
- 不绕过付费墙，不传播授权受限的论文全文。
- AI 生成的证明、引文和学术结论必须由研究者核验。
- 最终的正确性、新颖性、署名和投稿决定始终属于研究者。

## English

ScholarFlow is a Codex Skill that turns separate research tools into a repeatable, human-reviewed workflow. It builds a researcher profile, inspects the academic tools currently available, plans research tasks, routes literature discovery to the best available provider, and hands approved papers to Zotero and local LaTeX/TeXstudio.

It does not replace Consensus, Zotero, Wolfram, or academic databases. It coordinates them. When a preferred plugin is unavailable, ScholarFlow falls back to open sources while preserving queries, evidence, uncertainty, and human decisions.

Start in a new Codex task:

```text
Use $scholar-flow to learn my research profile, inspect my available research tools,
and start this week's paper radar. Ask me to choose Read / Save / Ignore.
```

## 日本語

ScholarFlow は、研究者プロフィールをもとに、論文検索ツール、Zotero、計算ツール、ローカルの TeXstudio/LaTeX を一つの反復可能な研究フローにつなぐ Codex Skill です。AI が候補と根拠を整理し、研究者が「精読・保存・除外」を判断します。

## 한국어

ScholarFlow는 연구자 프로필을 기반으로 논문 검색 도구, Zotero, 계산 도구, 로컬 TeXstudio/LaTeX를 반복 가능한 연구 흐름으로 연결하는 Codex Skill입니다. AI는 후보와 근거를 정리하고, 연구자는 정독·저장·제외를 결정합니다.

## Inspirations

- [research_LLM_wiki](https://github.com/jinleiphys/research_LLM_wiki): literature wiki and private research profile.
- [ai-research-skills](https://github.com/WenyuChiou/ai-research-skills): resumable state and human review gates.
- [ResearchClaw](https://github.com/ymx10086/ResearchClaw): literature discovery workflow patterns.

ScholarFlow is an independent implementation. It references workflow ideas rather than copying upstream source code.

## License

MIT
