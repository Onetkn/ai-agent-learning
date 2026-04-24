# 资源清单、论文来源与热点 Radar

原则：科研学习优先一手论文、开放评审、benchmark、代码仓库和官方文档。视频和社区讨论只用来辅助理解，不作为结论来源。

## Paper Reading

每周论文阅读分成三层，避免只读基础材料，也避免被热点牵着走。

### 三层阅读结构

- 经典/基础论文：用于补研究地基，深读并写完整笔记。
- 路线图相关论文：服务当前阶段主题，深读并关联本周研究问题。
- 热点前沿论文：追近 3-6 个月的新方向，速览 2-4 篇，只判断是否值得后续深读或复现。

### 每周默认配比

- 1 篇经典/基础深读。
- 1 篇路线图相关深读。
- 2-4 篇热点速览。
- 深读论文必须写入 `notes/`；热点速览可以先做表格记录，只有高价值论文再补完整笔记。

### 热点方向优先级

热点方向由每周自动化动态刷新，但默认优先看这些：

- Agent tool use / MCP benchmarks
- Agent memory and long-horizon interaction
- Agent evaluation and reliability
- Research agents / scientific discovery agents
- Coding agents and SWE-style benchmarks
- Browser / computer-use agents
- RAG vs long-context / retrieval evaluation
- Multi-agent coordination and protocol design

### 热点筛选标准

- 近 3-6 个月发表或更新优先。
- 顶会、期刊、OpenReview 高质量讨论、ACL Anthology、官方 benchmark 页面优先。
- 有 code、dataset、benchmark、复现材料或清晰实验设置优先。
- 只追和 LLM/Agent 科研主线可能发生关系的热点，不追产品新闻或框架营销。
- arXiv 可以看，但要额外检查作者、实验、代码、引用和是否进入会议/期刊流程。

## 论文来源优先级

### 开放评审与会议

- [OpenReview](https://openreview.net/)
- [ICLR 2026 papers](https://iclr.cc/virtual/2026/papers.html)
- [NeurIPS 2025 papers](https://neurips.cc/virtual/2025/papers.html?layout=detail)
- [ICML](https://icml.cc/)
- [COLM](https://colmweb.org/)
- [TMLR](https://jmlr.org/tmlr/)
- [JMLR](https://www.jmlr.org/)

### NLP 与 LLM 论文库

- [ACL Anthology](https://aclanthology.org/)
- [ACL Anthology 2025 Findings](https://aclanthology.org/events/findings-2025/)
- [EMNLP](https://2025.emnlp.org/)
- [NAACL](https://2025.naacl.org/)

### 热点与预印本

- [arXiv cs.CL](https://arxiv.org/list/cs.CL/recent)
- [arXiv cs.AI](https://arxiv.org/list/cs.AI/recent)
- [arXiv cs.LG](https://arxiv.org/list/cs.LG/recent)
- [Papers with Code](https://paperswithcode.com/)

## 近期热点参考入口

这些不是固定必读清单，而是每周 radar 的起点：

- [MCP-Bench: Benchmarking Tool-Using LLM Agents with Complex Real-World Tasks via MCP Servers](https://openreview.net/forum?id=fe8mzHwMxN)
- [Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://openreview.net/forum?id=DT7JyQC3MR)
- [NeurIPS Datasets & Benchmarks Track](https://nips.cc/virtual/2025/events/datasets-benchmarks-2025)
- [ACL Anthology 2025 Findings](https://aclanthology.org/events/findings-2025/)
- [ICLR 2026 accepted papers](https://iclr.cc/virtual/2026/papers.html)

## 官方与工程背景材料

这些材料不是主线终点，但有助于理解论文里的系统假设。

### 官方

- [OpenAI Agents SDK](https://developers.openai.com/api/docs/guides/agents-sdk)
- [OpenAI Agent Evals](https://developers.openai.com/api/docs/guides/agent-evals)
- [OpenAI Docs MCP](https://developers.openai.com/learn/docs-mcp)
- [Model Context Protocol](https://github.com/modelcontextprotocol)

### 框架与工程

- [Anthropic: Building Effective AI Agents](https://resources.anthropic.com/hubfs/Building%20Effective%20AI%20Agents-%20Architecture%20Patterns%20and%20Implementation%20Frameworks.pdf?hsLang=en)
- [PydanticAI](https://github.com/pydantic/pydantic-ai)
- [LangGraph Docs](https://langchain-ai.github.io/langgraphjs/reference/modules/langgraph.html)
- [LlamaIndex](https://github.com/run-llama/llama_index)
- [Phoenix Observability](https://github.com/Arize-ai/phoenix)
- [DSPy](https://github.com/stanfordnlp/dspy)

## Benchmark 入口

- [SWE-bench](https://www.swebench.com/)
- [GAIA Leaderboard](https://huggingface.co/gaia-benchmark)
- [OSWorld](https://os-world.github.io/)

## 论文阅读时必须回答的问题

每次深读至少回答下面问题：

- 这篇论文的问题定义是什么
- 它声称的贡献属于哪一类：方法、系统、benchmark、分析还是数据
- 它的 baseline 是否公平
- 它的 metric 是否真的测到了目标能力
- 它最强的证据是什么
- 它最弱或最可疑的地方是什么
- 哪个结论可以用最小工程实验验证
- 它暴露了什么新的研究问题

## YouTube / 社区的正确打开方式

可以用来快速理解背景，但不能替代论文。

适合看：

- benchmark 解读
- 论文 walkthrough
- agent 架构对比
- 复现经验

不适合看：

- “某框架最强”式争论
- 没有实验设置的效果宣称
- 单个 demo 推导研究结论
