# 第 3 周闭环冲刺周末 Reviewer 记录

日期：2026-06-16

对应周次：2026-06-08 至 2026-06-14（第 3 周闭环冲刺）
Reviewer：weekly-learning-reviewer

## 本周完成情况

本次检查以 2026-06-08 之后在 `notes/`、`experiments/`、`reports/`、`radar/` 中新增或更新的内容为准。结果显示：本周只新增了 1 条热点 radar，没有形成深读、问题卡、官方资料笔记或最小实验计划，因此整体应判定为“部分完成，且不足以推进到第 4 周阶段小结”。

### 产物检查

| 产物 | 状态 | 依据 |
| --- | --- | --- |
| 论文阅读笔记 | 缺失 | `notes/` 在本周时间窗内没有新增或更新文件；仓库里仍没有 `AgentBench` 正式深读笔记，说明还没有回答“问题、贡献、证据、局限、下一步验证”这组核心问题。 |
| 研究问题卡 | 缺失 | 本周没有新增研究问题卡，也没有把“verification vs trajectory diagnosis”收束成可证伪假设、验证边界和最小实验。 |
| 热点 radar | 完成 | [`/D:/Learning/radar/2026-06-week-02-hot-papers.md`](/D:/Learning/radar/2026-06-week-02-hot-papers.md) 在本周新增，内容不只是列链接，还明确给出“暂不深读、只保留方向感”的判断，并把 reliability、memory、browser、computer-use 四条支线和当前主线区分开。 |
| 官方文档或视频笔记 | 缺失 | 本周没有新增 `OpenAI Agent Evals`、`MCP Specification` 或 `Stanford CS25` 的正式笔记，因此还没有把辅助材料转成对 benchmark / eval 理解的补充证据。 |
| 最小实验 / 复现计划 | 缺失 | `experiments/` 本周没有新增或更新文件；目标文件 `experiments/2026-06-week-02-agentbench-vs-mcpmark-plan.md` 仍不存在，说明对 benchmark 设计差异的判断还停在计划层。 |
| 周复盘 | 部分完成 | 仓库里没有用户侧独立周复盘；本次 reviewer 补上了状态判断、缺口和补救建议，但“学习者自己的复盘沉淀”仍未单独留下。 |

## 最有价值的判断

1. 这周最有价值的不是新增资料，而是 `radar` 已经明确说明哪些热点该延后，避免 browser、memory、safety 抢走当前闭环任务。
2. 当前真正的瓶颈仍然不是选题，而是没有把已有主线写成正式产物；也就是“知道该读什么”还没有转成“留下了什么证据与判断”。
3. 因此最值得保住的不是继续扩 `radar`，而是把已有主线压缩成 1 篇深读、1 张问题卡、1 个最小实验设计这三件套。

## 最大缺口

最大缺口仍然是缺少一份真正回答下面问题的核心产物：

> `AgentBench` 和 `MCPMark` 的 benchmark 结论，到底更多来自任务环境设计、verification 粒度，还是 trajectory-level diagnosis？

现在仓库里已有足够的路线图、热点判断和候选资源，但没有任何一份本周新增文档把这个问题推进到“可验证、可反驳、可继续实验”的状态。

## 需要降载还是推进

建议：继续降载，不推进到第 4 周。

依据：

- 本周只完成了 1 条 `radar`，未达到 [`/D:/Learning/docs/04-weekly-operating-system.md`](/D:/Learning/docs/04-weekly-operating-system.md) 中每周 DoD 的最低闭环要求。
- 第 3 周计划中的三件核心产物仍然全部缺失：深读笔记缺失，问题卡缺失，最小实验缺失。
- `radar` 已经证明资料面并不短缺；继续扩资料只会继续放大 backlog，而不会提升研究判断密度。

## 下周建议主题

下周只保留一个主题：

> 用 `AgentBench` 作为旧 benchmark 基线，用 `MCPMark` 作为真实工具环境 benchmark 对照，判断 verification 与 trajectory diagnosis 是否是主要增量。

## 建议阅读材料类型

1. 1 篇深读 benchmark 论文：`AgentBench: Evaluating LLMs as Agents`
2. 1 份官方文档：`OpenAI Agent Evals`
3. 1 份协议边界文档：`MCP Specification`

## 建议最小实验

实验目标：
把 `AgentBench` 和 `MCPMark` 抽成一张固定字段对比表，验证“新一代 MCP benchmark 的主要增量是否真的来自 verification 与诊断层，而不只是任务更多”。

最小设计：

- 输入：两篇论文的 experiment / evaluation 章节
- 固定字段：任务环境、工具空间、baseline 类型、metric / verification、failure mode
- 输出：1 张对比表 + 1 段 150-300 字判断
- 边界：不写代码，不扩第三篇 benchmark，不做复现实现

## 降载补救计划

如果下周时间仍然有限，只保留以下三项：

1. 1 篇深读论文笔记
   目标文件：`notes/2026-06-week-03-agentbench-reading-note.md`
2. 1 张研究问题卡
   目标文件：`notes/2026-06-week-03-research-question-benchmark-verification-vs-trajectory.md`
3. 1 个最小实验设计
   目标文件：`experiments/2026-06-week-03-agentbench-vs-mcpmark-plan.md`

## Reviewer 建议

- 不继续新增热点资料，先把已有 `radar` 中的判断转成正式产物。
- 下周只允许围绕一个问题写作，避免同时扩到 browser、memory、safety 三条线。
- 如果三件套仍未齐全，下一次 reviewer 应继续按“缺失”处理，而不是因为已有计划和 radar 就默认部分完成。
