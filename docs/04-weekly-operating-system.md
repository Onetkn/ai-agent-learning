# 每周科研推进系统

你每周只有 6-8 小时，所以关键不是塞满资料，而是固定完成“读论文 -> 提问题 -> 小验证 -> 复盘”的闭环。

## 默认时间分配

- 论文阅读：40%
- 问题整理：20%
- 复现/实验：30%
- 复盘：10%

### 6 小时版

- 2.5 小时：深读 2 篇论文
- 1 小时：速览 2-4 篇热点论文并做 radar 记录
- 1.5 小时：做最小复现、ablation 或实验设计
- 1 小时：写研究问题卡和周复盘

### 8 小时版

- 3 小时：深读 2 篇论文
- 1 小时：热点速览
- 2.5 小时：复现/实验
- 1.5 小时：问题卡、related work、周复盘

## 每周 Definition of Done

一周结束前至少留下这些产物：

- 1 篇完整论文阅读笔记
- 1 张研究问题卡
- 1 条热点 radar 记录
- 1 个最小实验、复现实验设计或失败分析

如果时间紧，优先保留“论文笔记 + 研究问题卡”。代码可以小，但问题必须清楚。

## 每周 Paper Reading 规则

### 深读

- 1 篇经典/基础论文：用于补地基。
- 1 篇路线图相关论文：用于推进当前阶段主题。

深读论文必须回答：

- 论文解决什么问题
- 方法和 baseline 分别是什么
- metric 是否合理
- 实验是否支撑结论
- 有什么局限
- 哪个结论可以被最小复现

### 热点速览

每周速览 2-4 篇近 3-6 个月热点论文。速览只做判断：

- 是否真的与 LLM/Agent 科研主线相关
- 是新问题、新 benchmark、新方法，还是旧问题换包装
- 是否有 code、dataset、benchmark 或开放评审
- 是否值得下周深读或复现

默认热点方向：

- Agent tool use / MCP benchmarks
- Agent memory and long-horizon interaction
- Agent evaluation and reliability
- Research agents / scientific discovery agents
- Coding agents and SWE-style benchmarks
- Browser / computer-use agents
- RAG vs long-context / retrieval evaluation
- Multi-agent coordination and protocol design

## 每周固定动作

### 周开始

- 根据 `docs/01-roadmap.md` 确认本周阶段主题。
- 选 2 篇深读论文和 2-4 篇热点速览论文。
- 明确本周只回答 1 个研究问题。

### 周中

- 写论文阅读笔记，不只写摘要。
- 把论文里的 claim 转成可验证假设。
- 记录至少 3 个不确定点或反例。

### 周末

- 更新周复盘。
- 沉淀 1 张研究问题卡。
- 判断本周问题是否进入后续复现、survey 或放弃。

## 研究问题标准

每周必须沉淀一个“研究问题”。它不是“这篇论文讲了什么”，而是：

- 这篇论文暴露了什么未解决问题
- 现有证据哪里不够强
- 哪个结论可能只在特定 setting 下成立
- 我能否用小实验验证或挑战它

一个好的研究问题通常长这样：

- 当工具数量增加时，agent 的错误主要来自工具选择还是参数构造？
- RAG 的 rerank 提升是否会在 citation faithfulness 上带来副作用？
- Memory agent 的长期记忆是否会引入过时信息污染？
- MCP benchmark 是否真的测到了多工具协调，还是只测到了工具描述理解？

## 学习文件使用建议

- `notes/`：放论文阅读笔记、related work、概念解释。
- `experiments/`：放复现记录、ablation、benchmark 再分析。
- `reports/`：放阶段 survey、研究报告、公开作品文稿。
- `projects/`：放最小工程原型，不追求产品完整度。

## 推荐命名

- `notes/2026-04-paper-mcp-bench.md`
- `notes/2026-04-research-question-tool-selection.md`
- `experiments/2026-05-rag-rerank-ablation.md`
- `reports/phase-3-rag-long-context-survey.md`
- `projects/project-03-research-agent/README.md`

## 什么时候允许切换主题

只有满足下面任一条件才切：

- 当前主题已经形成阶段 survey。
- 当前研究问题已被证伪或证明过大，需要重写。
- 新热点和当前主线高度相关，且能形成可验证问题。

否则继续深挖，不要被新论文标题牵着跑。
