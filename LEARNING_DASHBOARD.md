# Learning Dashboard

这个文件是仓库入口。每周先看这里，再进入 `planning/current-week.md` 执行。

## 当前状态

- 当前定位：LLM / Agent 科研学习陪伴系统
- 路线图位置：24 周路线图第 1 阶段“研究入门与论文阅读方法”
- 真实进度判断：第 1-2 周已有正式产物；截至 2026-06-22，仍停留在第 3 周“实验拆解与评测意识”，尚不进入第 4 周阶段小结
- 最近事实：2026-06-15 至 2026-06-21 新增了 `radar/2026-06-week-03-hot-papers.md` 和周计划，但 `notes/`、`experiments/` 仍没有 `AgentBench` 正式深读笔记、研究问题卡或最小实验计划
- 当前主线：从“会看概念”推进到“会拆 benchmark / dataset / baseline / metric / verification / failure case”
- 本周最小推进：继续补齐 `AgentBench` 深读笔记、研究问题卡、`AgentBench` vs `MCPMark` 最小实验计划三件套；只有三件套完成后，才允许进入第 4 周阶段小结

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
- 已归档计划、reviewer 与 radar
  - `planning/2026-04-week-01.md`
  - `planning/2026-05-week-03.md`
  - `planning/2026-06-week-01.md`
  - `planning/2026-06-week-02.md`
  - `planning/2026-06-week-03.md`
  - `radar/2026-05-week-03-hot-papers.md`
  - `radar/2026-06-week-01-hot-papers.md`
  - `radar/2026-06-week-02-hot-papers.md`
  - `radar/2026-06-week-03-hot-papers.md`
  - `reports/2026-06-week-02-reviewer.md`

## 为什么本周仍不进入第 4 周

- 第 4 周要求阶段 survey、3 张候选研究问题卡，以及“工程实现能验证什么、不能验证什么”的说明。
- 但第 3 周的证据底座仍缺 3 个正式产物：`AgentBench` 深读笔记、benchmark/eval 研究问题卡、`AgentBench` vs `MCPMark` 最小实验计划。
- 2026-05-17、2026-05-31、2026-06-08、2026-06-16 的 reviewer 判断都指向同一个问题：资料已经够，闭环没有落盘。
- 因此 2026-06-22 至 2026-06-28 的正确动作仍是降载收口，而不是扩到 memory、browser、scientific agent 或 coding agent 深读。

## 本周资源组合：2026-06-22 至 2026-06-28

| 类型 | 资源 | 为什么现在读 |
| --- | --- | --- |
| 经典 / 基础深读 | [AgentBench: Evaluating LLMs as Agents](https://openreview.net/forum?id=zAdUB0aCTQ) | 用较早的系统 benchmark 训练拆解 task、environment、baseline、metric、verification 和 failure analysis，是第 3 周必须补齐的地基 |
| 路线图相关深读 | [MCPMark: A Benchmark for Stress-Testing Realistic and Comprehensive MCP Use](https://openreview.net/forum?id=uobROwBsJm) | OpenReview 页面显示它围绕 Notion、GitHub、Filesystem、PostgreSQL、Playwright 等真实 MCP 场景构造 127 个任务，适合和 `AgentBench` 对比“真实工具环境”带来的评测增量 |
| 热点速览 | `radar/2026-06-week-04-hot-papers.md` | 只维护方向感，重点看 MCP/tool-use、memory、computer-use、user-aware evaluation 四类 benchmark 如何细化诊断，不新增深读债务 |
| 官方文档 | [OpenAI Agent Evals](https://developers.openai.com/api/docs/guides/agent-evals) | 官方文档把 traces、graders、datasets、eval runs 放在 agent workflow 质量改进链条里，正好补足论文 benchmark 与工程 eval 的对应关系 |
| 协议文档 | [Model Context Protocol 2025-06-18 Specification](https://modelcontextprotocol.io/specification/2025-06-18) | 官方规范说明 MCP 用于连接 LLM 应用与外部数据源和工具，并以 `schema.ts` 为权威协议要求来源，适合确认 tool-use benchmark 的协议边界 |
| 课程 / talk | [Stanford CS25 V5: RL as a Co-Design of Product and Research](https://web.stanford.edu/class/cs25/past/cs25-v5/) | 该 talk 强调产品原型、用户反馈与 eval 指标的共同设计，能补足论文里不容易展开的真实反馈视角 |
| 最小实验 | `experiments/2026-06-week-04-agentbench-vs-mcpmark-plan.md` | 不写代码，只做两篇 benchmark 的固定字段对比表，把“新一代 MCP benchmark 新增了什么难点”写成可检查判断 |

## 本周必须产出

- 1 篇论文深读笔记
  - `notes/2026-06-week-04-agentbench-reading-note.md`
- 1 张研究问题卡
  - `notes/2026-06-week-04-research-question-benchmark-verification-vs-trajectory.md`
- 1 条热点 radar
  - `radar/2026-06-week-04-hot-papers.md`
- 1 份官方文档或视频笔记
  - `notes/2026-06-week-04-openai-agent-evals-note.md` 或 `notes/2026-06-week-04-cs25-eval-note.md`
- 1 个最小实验 / 复现计划
  - `experiments/2026-06-week-04-agentbench-vs-mcpmark-plan.md`

如果本周时间不足，自动降载为：

- 1 篇 `AgentBench` 深读笔记
- 1 张研究问题卡
- 1 个下周继续计划

## 当前活跃研究问题

> `AgentBench` 和 `MCPMark` 的 benchmark 结论，究竟主要受任务环境、验证方式，还是 trajectory-level diagnosis 影响？

本周写作时只围绕这个问题，不扩成新的 survey。

## 本周执行顺序

1. 先完成 `AgentBench` 正式深读笔记，重点拆 experiment / evaluation / failure analysis。
2. 用 `OpenAI Agent Evals` 或 `Stanford CS25` 补一份非论文笔记，写清它补足了哪块理解。
3. 完成 `AgentBench` vs `MCPMark` 的固定字段对比表。
4. 把判断收束成 1 张研究问题卡。
5. 周末只判断一件事：三件套是否足以支撑进入第 4 周阶段小结。

## 当前 Backlog

- `notes/2026-06-week-04-agentbench-reading-note.md`
- `notes/2026-06-week-04-research-question-benchmark-verification-vs-trajectory.md`
- `experiments/2026-06-week-04-agentbench-vs-mcpmark-plan.md`
- `notes/2026-06-week-04-openai-agent-evals-note.md` 或 `notes/2026-06-week-04-cs25-eval-note.md`
- 第 4 周阶段小结暂缓，等第 3 周三件套完成后再启动

## 每周操作顺序

1. 打开 `planning/current-week.md`
2. 先完成 1 篇深读，再补 1 份非论文笔记
3. 在 `radar/` 里速览 2-4 篇近 3-6 个月热点论文
4. 用最小实验把 1 个 benchmark claim 变成可验证对比
5. 周末只判断一件事：第 3 周三件套是否闭环，是否允许进入第 4 周
