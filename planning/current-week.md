# Current Week Plan

周次：第 3 周闭环冲刺

日期：2026-06-08 至 2026-06-14

主研究主题：不扩新主题，先把阶段 1 第 3 周真正闭环，用 benchmark / eval 视角完成正式产物

## 这周为什么还不能进第 4 周

- 截至 2026-06-08，仓库稳定完成的正式产物仍停在第 1-2 周。
- 过去两次 reviewer 结论一致：缺的不是资料面，而是没有把 `AgentBench` 主线落成正式笔记、问题卡和最小实验。
- 因此这周继续停留在“实验拆解与评测意识”，目标不是找更多论文，而是把第 3 周三件套补完整。

## 本周能力目标

- 能拆一篇 agent benchmark 论文的实验设置：task、environment、baseline、metric、verification、failure mode。
- 能说明 `success rate` 之外，verification 与 trajectory diagnosis 为什么会改变 benchmark 的解释力。
- 能把一份官方文档或一场 talk 变成“补哪块理解”的正式笔记，而不是只保留链接。
- 能用一张固定字段对比表，把 `AgentBench` 和 `MCPMark` 的设计差异写成自己的判断。

## 本周资源组合

| 类型 | 资源 | 为什么这周读 |
| --- | --- | --- |
| 经典 / 基础深读 | [AgentBench: Evaluating LLMs as Agents](https://openreview.net/forum?id=zAdUB0aCTQ) | 用较早 benchmark 练习拆环境、baseline、metric、verification 与 failure analysis，是本周最该优先完成的正式深读。 |
| 路线图相关深读 | [MCPMark: A Benchmark for Stress-Testing Realistic and Comprehensive MCP Use](https://openreview.net/forum?id=uobROwBsJm) | OpenReview 显示发布于 2026-01-26，ICLR 2026 Poster；它仍是当前 MCP / tool-use benchmark 主线里最直接的路线图论文。 |
| 热点速览 | `radar/2026-06-week-02-hot-papers.md` | 只保留方向感，不新增深读债务。 |
| 官方文档 | [OpenAI Agent Evals](https://platform.openai.com/docs/guides/agent-evals) | 把论文里的 dataset、grader、trace grading、eval run 映射到工程 eval 结构。 |
| 协议文档 | [MCP Specification](https://modelcontextprotocol.io/specification) | 分清 host / client / server 与 tools / resources / prompts 的协议边界。 |
| 课程 / talk | [Stanford CS25 V5: RL as a Co-Design of Product and Research](https://web.stanford.edu/class/cs25/past/cs25-v5/) | 补“真实反馈如何塑造 eval 指标”的直觉，避免只盯 leaderboard。 |
| 最小实验 | `experiments/2026-06-week-02-agentbench-vs-mcpmark-plan.md` | 只做两篇 benchmark 的固定字段对比，不扩第三篇论文，不做大复现。 |

## 本周热点速览范围

这周只速览，不新增深读任务：

- [MCP-SafetyBench: A Benchmark for Safety Evaluation of Large Language Models with Real-World MCP Servers](https://openreview.net/forum?id=7XYjeL46co)
- [Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://openreview.net/forum?id=DT7JyQC3MR)
- [CAP: A Scalable Benchmark for Evaluating Cross-Site Browser Agents with Complex Actions and Perception](https://openreview.net/forum?id=05BubhVB4C)
- [OSWorld-MCP: Benchmarking MCP Tool Invocation In Computer-Use Agents](https://openreview.net/forum?id=rceD6wwt4B)

## 本周最小实验 / 复现计划

目标文件：

- `experiments/2026-06-week-02-agentbench-vs-mcpmark-plan.md`

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
  - `notes/2026-06-week-02-agentbench-reading-note.md`
- 研究问题卡：
  - `notes/2026-06-week-02-research-question-benchmark-verification-vs-trajectory.md`
- 官方文档或视频笔记：
  - `notes/2026-06-week-02-openai-agent-evals-note.md`
  - 或 `notes/2026-06-week-02-cs25-eval-note.md`
- 热点 radar：
  - `radar/2026-06-week-02-hot-papers.md`
- 最小实验：
  - `experiments/2026-06-week-02-agentbench-vs-mcpmark-plan.md`

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

## 允许推进到第 4 周的条件

只有同时满足下面三条，才允许下周进入第 4 周阶段小结：

- 已完成 `AgentBench` 正式深读笔记
- 已完成研究问题卡
- 已完成 `AgentBench` vs `MCPMark` 最小实验计划

如果任一项缺失，下周继续降载，不扩新主题。

## 周末复盘 Checklist

- [ ] 是否完成 `notes/2026-06-week-02-agentbench-reading-note.md`？
- [ ] 是否完成 1 份官方文档或 talk 笔记，并写清它补足了哪块理解？
- [ ] 是否完成 `radar/2026-06-week-02-hot-papers.md`？
- [ ] 是否完成 `experiments/2026-06-week-02-agentbench-vs-mcpmark-plan.md`？
- [ ] 是否完成 `notes/2026-06-week-02-research-question-benchmark-verification-vs-trajectory.md`？
- [ ] 是否满足进入第 4 周的三项条件？

## 如果时间只有 3 小时

只保留这三件事：

1. 深读 `AgentBench` 并写 1 篇笔记
2. 写 1 张研究问题卡
3. 写出下周继续计划，不扩新论文

## Reviewer 建议（2026-06-08）

- 上周实际完成：`radar/2026-06-week-01-hot-papers.md`
- 上周仍缺：`AgentBench` 深读笔记、研究问题卡、`AgentBench` vs `MCPMark` 最小实验计划、1 份官方文档或 talk 笔记
- reviewer 判断：上周整体为“部分完成”，但仍不足以推进到第 4 周
- 本周执行原则：继续降载，只围绕一个问题补三件套，不新增 browser、memory、safety 的深读债务
- 本周最低交付：
  1. `notes/2026-06-week-02-agentbench-reading-note.md`
  2. `notes/2026-06-week-02-research-question-benchmark-verification-vs-trajectory.md`
  3. `experiments/2026-06-week-02-agentbench-vs-mcpmark-plan.md`

## Reviewer 建议（2026-06-16）

- 本周实际完成：`radar/2026-06-week-02-hot-papers.md`
- 本周仍缺：`AgentBench` 深读笔记、研究问题卡、`AgentBench` vs `MCPMark` 最小实验计划、1 份官方文档或协议笔记
- reviewer 判断：本周整体仍为“部分完成”，但不足以推进到第 4 周；当前瓶颈依旧是没有把已有主线落成正式产物
- 下周执行原则：继续降载，不新增 browser、memory、safety 深读任务，只围绕一个 benchmark 问题补三件套
- reviewer 建议的最低交付：
  1. `notes/2026-06-week-03-agentbench-reading-note.md`
  2. `notes/2026-06-week-03-research-question-benchmark-verification-vs-trajectory.md`
  3. `experiments/2026-06-week-03-agentbench-vs-mcpmark-plan.md`
