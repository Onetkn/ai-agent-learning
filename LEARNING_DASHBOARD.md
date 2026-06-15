# Learning Dashboard

这个文件是仓库入口。每周先看这里，再进入 `planning/current-week.md` 执行。

## 当前状态

- 当前定位：LLM / Agent 科研学习陪伴系统
- 路线图位置：24 周路线图第 1 阶段“研究入门与论文阅读方法”
- 真实进度判断：已稳定完成第 1-2 周产物；截至 2026-06-16，仍停留在第 3 周主题“实验拆解与评测意识”，尚未进入第 4 周阶段小结
- 最近事实：`notes/` 与 `experiments/` 自 2026-04-20 后没有新增正式产物；2026-06-09 至 2026-06-15 之间也没有新笔记或新实验落盘
- 当前主线：从“会看概念”推进到“会拆 benchmark / dataset / baseline / metric / verification / failure case”
- 本周最小推进：先补齐 `AgentBench` 深读笔记、研究问题卡、`AgentBench` vs `MCPMark` 最小实验设计三件套；如果还有余力，再补 1 份 `OpenAI Agent Evals` 或 `Stanford CS25` 笔记

## 已完成产物

- 论文 / 概念笔记
  - `notes/2026-04-week-01-prompt-tool-workflow.md`
  - `notes/2026-04-week-01-glossary.md`
  - `notes/2026-04-week-02-structured-extractor-design.md`
- 实验 / 验证资产
  - `experiments/2026-04-week-01-zero-shot-vs-few-shot.md`
  - `experiments/2026-04-week-02-structured-extractor-samples.md`
- 项目约束文档
  - `projects/project-01-structured-extractor/2026-04-week-02-schema.md`
- 已归档计划与 radar
  - `planning/2026-05-week-03.md`
  - `planning/2026-06-week-01.md`
  - `planning/2026-06-week-02.md`
  - `radar/2026-05-week-03-hot-papers.md`
  - `radar/2026-06-week-01-hot-papers.md`
  - `radar/2026-06-week-02-hot-papers.md`
  - `radar/2026-06-week-03-hot-papers.md`

## 为什么本周仍不进入第 4 周

- `notes/`、`experiments/` 里仍缺第 3 周应有的正式深读笔记、问题卡和最小实验计划。
- 2026-05-17、2026-05-31、2026-06-08 三次 reviewer 结论都指向同一个问题：资料已经够了，但闭环没有落盘。
- 因此 2026-06-16 这一周的正确动作仍然不是扩新主题，而是继续把 benchmark / eval 主线补成正式产物，再决定是否进入第 4 周。

## 本周资源组合（2026-06-15 至 2026-06-21）

| 类型 | 资源 | 为什么现在读 |
| --- | --- | --- |
| 经典 / 基础深读 | [AgentBench: Evaluating LLMs as Agents](https://openreview.net/forum?id=zAdUB0aCTQ) | 作为较早的系统 benchmark，最适合继续训练“怎么拆任务环境、baseline、metric、verification 与结论边界” |
| 路线图相关深读 | [MCPMark: A Benchmark for Stress-Testing Realistic and Comprehensive MCP Use](https://openreview.net/forum?id=uobROwBsJm) | OpenReview 显示发布于 2026-01-26，ICLR 2026 Poster；它仍是当前 MCP / tool-use benchmark 主线最直接的路线图论文 |
| 热点速览 | `radar/2026-06-week-03-hot-papers.md` | 用 4 篇近 3-6 个月热点论文维持方向感，但不再扩充新的深读债务 |
| 官方文档 | [OpenAI Agent Evals](https://developers.openai.com/api/docs/guides/agent-evals) | 官方页面强调用 traces、graders、datasets、eval runs 改进 agent 质量，正好对应本周 benchmark / eval 主线 |
| 协议文档 | [MCP Specification (2025-11-25)](https://modelcontextprotocol.io/specification/2025-11-25) | 当前官方规范入口明确 MCP 是连接 LLM 应用与外部数据源、工具的开放协议，并以 `schema.ts` 为权威来源 |
| 课程 / talk | [Stanford CS25 V5: RL as a Co-Design of Product and Research](https://web.stanford.edu/class/cs25/past/cs25-v5/) | Stanford 页面显示 2026-04-08 的 talk 直接讨论“真实用户反馈如何塑造 eval 指标”，能补足产品反馈视角 |
| 最小实验 | `experiments/2026-06-week-03-agentbench-vs-mcpmark-plan.md` | 继续只做两篇 benchmark 的固定字段对比，重点是写出自己的验证判断，而不是扩展第三篇论文 |

## 本周必须产出

- 1 篇论文深读笔记
  - `notes/2026-06-week-03-agentbench-reading-note.md`
- 1 张研究问题卡
  - `notes/2026-06-week-03-research-question-benchmark-verification-vs-trajectory.md`
- 1 条热点 radar
  - `radar/2026-06-week-03-hot-papers.md`
- 1 份官方文档或视频笔记
  - `notes/2026-06-week-03-openai-agent-evals-note.md` 或 `notes/2026-06-week-03-cs25-eval-note.md`
- 1 个最小实验 / 复现计划
  - `experiments/2026-06-week-03-agentbench-vs-mcpmark-plan.md`

如果本周时间不足，自动降载为：

- 1 篇深读论文笔记
- 1 张研究问题卡
- 1 个下周继续计划

## 当前活跃研究问题

- `AgentBench` 的低 success rate 中，有多少来自任务环境复杂度，有多少来自 verification 粒度不足？
- `MCPMark` 引入真实工具空间后，新增难点主要来自 CRUD 深度、状态验证，还是工具选择本身？
- trajectory-level diagnosis 相比最终 success rate，是否真的提高了 benchmark 结论的可解释性？

## 下周最小推进

只做一个最小但高价值的推进：

1. 深读 `AgentBench` 的实验与 failure analysis，完成正式笔记。
2. 用 `OpenAI Agent Evals` 或 `Stanford CS25` 补一页“论文指标 -> 工程 eval / 产品反馈对应关系”。
3. 写完 `AgentBench` vs `MCPMark` 的固定字段对比表，再决定是否进入第 4 周阶段小结。

## 当前 Backlog

- `notes/2026-06-week-03-agentbench-reading-note.md`
- `notes/2026-06-week-03-research-question-benchmark-verification-vs-trajectory.md`
- `experiments/2026-06-week-03-agentbench-vs-mcpmark-plan.md`
- `notes/2026-06-week-03-openai-agent-evals-note.md` 或 `notes/2026-06-week-03-cs25-eval-note.md`
- browser / memory / research-agent / coding-agent 几条热点线暂不扩深读，只保留在 `radar/` 做候选

## 每周操作顺序

1. 打开 `planning/current-week.md`
2. 先完成 1 篇深读，再补 1 份非论文笔记
3. 在 `radar/` 里速览 2-4 篇近 3-6 个月热点论文
4. 用最小实验把 1 个 benchmark claim 变成可验证对比
5. 周末只判断一件事：第 3 周三件套是否闭环，是否允许进入第 4 周

## Reviewer 历史结论

- 2026-05-17：建议降载，先补 `AgentBench` 深读笔记、研究问题卡、最小实验设计
- 2026-05-31：再次建议继续降载，说明闭环问题尚未解决，不应扩展新主题
- 2026-06-08：本周仅完成 `radar/2026-06-week-01-hot-papers.md`，整体判定为部分完成；继续降载，不进入第 4 周
