# Current Week Plan

周次：第 3 周收口 / 第 4 周前置准备

日期：2026-06-15 至 2026-06-21

主研究主题：继续完成阶段 1 第 3 周缺失产物，但这周的判断目标已经前置到“是否允许进入第 4 周阶段小结”

## 为什么这周仍然不直接切到第 4 周

- 截至 2026-06-16，`notes/` 与 `experiments/` 里仍没有 `AgentBench` 正式深读笔记、研究问题卡和最小实验计划。
- 也就是说，路线图上的“第 4 周应该写阶段 survey 和候选研究问题卡”，目前还缺第 3 周的证据底座。
- 因此这周的正确动作不是扩新论文，而是用最小资源组合把第 3 周收口，并为第 4 周阶段小结准备材料。

## 本周能力目标

- 能拆一篇 agent benchmark 论文的实验设置：task、environment、baseline、metric、verification、failure mode。
- 能说明 `success rate` 之外，verification 与 trajectory diagnosis 为什么会改变 benchmark 的解释力。
- 能把一份官方文档或一场 talk 变成“补哪块理解”的正式笔记，而不是只保留链接。
- 能用一张固定字段对比表，把 `AgentBench` 和 `MCPMark` 的设计差异写成自己的判断。
- 能在周末只回答一个关键信号：第 3 周三件套是否足以支撑进入第 4 周阶段小结。

## 本周资源组合

| 类型 | 资源 | 为什么这周读 |
| --- | --- | --- |
| 经典 / 基础深读 | [AgentBench: Evaluating LLMs as Agents](https://openreview.net/forum?id=zAdUB0aCTQ) | 继续用较早 benchmark 练习拆环境、baseline、metric、verification 与 failure analysis，是这周最该优先完成的正式深读。 |
| 路线图相关深读 | [MCPMark: A Benchmark for Stress-Testing Realistic and Comprehensive MCP Use](https://openreview.net/forum?id=uobROwBsJm) | OpenReview 显示发布于 2026-01-26，ICLR 2026 Poster；它仍是当前 MCP / tool-use benchmark 主线里最直接的路线图论文。 |
| 热点速览 | `radar/2026-06-week-03-hot-papers.md` | 本周只维持方向感，避免再扩深读债务。 |
| 官方文档 | [OpenAI Agent Evals](https://developers.openai.com/api/docs/guides/agent-evals) | 官方页面明确用 traces、graders、datasets、eval runs 评估 agent workflows，能直接补 benchmark 与工程 eval 的映射。 |
| 协议文档 | [MCP Specification (2025-11-25)](https://modelcontextprotocol.io/specification/2025-11-25) | 当前官方规范入口强调 MCP 是连接 LLM 应用与外部数据源、工具的开放协议，并以 `schema.ts` 为权威来源。 |
| 课程 / talk | [Stanford CS25 V5: RL as a Co-Design of Product and Research](https://web.stanford.edu/class/cs25/past/cs25-v5/) | Stanford 页面显示 2026-04-08 的 talk 直接讨论“真实用户反馈如何塑造 eval 指标”，适合补产品反馈视角。 |
| 最小实验 | `experiments/2026-06-week-03-agentbench-vs-mcpmark-plan.md` | 继续只做两篇 benchmark 的固定字段对比，不扩第三篇论文，不做大复现。 |

## 本周热点速览范围

这周只速览，不新增深读任务：

- [AstaBench: Rigorous Benchmarking of AI Agents with a Scientific Research Suite](https://openreview.net/forum?id=M7TNf5J26u)
- [RECODE-H: A Benchmark for Research Code Development with Interactive Human Feedback](https://openreview.net/forum?id=IKnuyyPHCV)
- [MCP-SafetyBench: A Benchmark for Safety Evaluation of Large Language Models with Real-World MCP Servers](https://openreview.net/forum?id=7XYjeL46co)
- [Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://openreview.net/forum?id=DT7JyQC3MR)

## 本周最小实验 / 复现计划

目标文件：

- `experiments/2026-06-week-03-agentbench-vs-mcpmark-plan.md`

只做一个轻量实验，不做完整代码复现：

1. 读 `AgentBench` 和 `MCPMark` 的实验与评测章节。
2. 抽一张固定字段对比表：
   - 任务环境
   - 工具空间
   - baseline 类型
   - metric / verification
   - 主要 failure mode
3. 最后只回答一句：
   - 新一代 MCP benchmark 真正新增的评测难点是什么？

## 本周必须产出

- 论文笔记：
  - `notes/2026-06-week-03-agentbench-reading-note.md`
- 研究问题卡：
  - `notes/2026-06-week-03-research-question-benchmark-verification-vs-trajectory.md`
- 官方文档或视频笔记：
  - `notes/2026-06-week-03-openai-agent-evals-note.md`
  - 或 `notes/2026-06-week-03-cs25-eval-note.md`
- 热点 radar：
  - `radar/2026-06-week-03-hot-papers.md`
- 最小实验：
  - `experiments/2026-06-week-03-agentbench-vs-mcpmark-plan.md`

## 本周研究问题卡

建议问题：

> `AgentBench` 和 `MCPMark` 的 benchmark 结论，究竟主要受任务环境、验证方式，还是 trajectory-level diagnosis 影响？

写卡时至少回答：

- 这个问题对应哪两篇论文
- 现有证据链最弱的环节在哪
- 我能用什么最小对比把这个问题继续逼近

## 本周执行顺序

1. 先深读 `AgentBench`，把正式笔记写出来
2. 再补 1 份 `OpenAI Agent Evals` 或 `Stanford CS25` 笔记
3. 再写 `AgentBench` vs `MCPMark` 的固定字段对比表
4. 最后把判断收束成 1 张研究问题卡
5. 周末只决定一件事：是否允许下周正式进入第 4 周阶段小结

## 允许推进到第 4 周的条件

只有同时满足下面三条，才允许下周进入第 4 周阶段小结：

- 已完成 `AgentBench` 正式深读笔记
- 已完成研究问题卡
- 已完成 `AgentBench` vs `MCPMark` 最小实验计划

如果任一项缺失，下周继续降载，不扩新主题。

## 周末复盘 Checklist

- [ ] 是否完成 `notes/2026-06-week-03-agentbench-reading-note.md`？
- [ ] 是否完成 1 份官方文档或 talk 笔记，并写清它补足了哪块理解？
- [ ] 是否完成 `radar/2026-06-week-03-hot-papers.md`？
- [ ] 是否完成 `experiments/2026-06-week-03-agentbench-vs-mcpmark-plan.md`？
- [ ] 是否完成 `notes/2026-06-week-03-research-question-benchmark-verification-vs-trajectory.md`？
- [ ] 是否满足进入第 4 周的三项条件？

## 如果时间只有 3 小时

只保留这三件事：

1. 深读 `AgentBench` 并写 1 篇笔记
2. 写 1 张研究问题卡
3. 写出下周继续计划，不扩新论文

## 本周阶段判断

- 如果三件套完成：下周进入第 4 周，写阶段 1 小结、3 张候选研究问题卡和“工程验证能做什么 / 不能做什么”说明。
- 如果三件套未完成：继续停留在阶段 1 第 3 周，不要切换到 memory、browser、scientific agents 或 coding agents 深读。
