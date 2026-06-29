# 第 4 周周末 Reviewer 记录

日期：2026-06-29

对应周次：2026-06-22 至 2026-06-28（第 3 周二次收口 / 第 4 周前置准备）
Reviewer：weekly-learning-reviewer

## 本周完成情况

本次检查以 2026-06-22T13:50:09Z 之后在 `notes/`、`experiments/`、`reports/`、`radar/` 中新增或更新的内容为准。实际新增的学习产物只有 `radar/2026-06-week-04-hot-papers.md`；`notes/` 与 `experiments/` 没有 week-04 的正式深读、问题卡、官方文档或视频笔记、最小实验计划。因此整体判定为：本周仅完成热点跟踪，核心学习闭环仍明显不足。

### 产物检查

| 产物 | 状态 | 依据 |
| --- | --- | --- |
| 论文阅读笔记 | 缺失 | 本周时间窗内 `notes/` 没有任何新增或更新文件；目标文件 `notes/2026-06-week-04-agentbench-reading-note.md` 仍不存在，因此还没有回答 `AgentBench` 的问题、贡献、实验设置、证据边界和可复现点。 |
| 研究问题卡 | 缺失 | 没有新增 `notes/2026-06-week-04-research-question-benchmark-verification-vs-trajectory.md`；当前研究问题只停留在 dashboard 和计划层，没有写成可证伪假设、最小验证方案和边界条件。 |
| 热点 radar | 完成 | `radar/2026-06-week-04-hot-papers.md` 已新增，内容不仅列出 MCP/tool-use、memory、computer-use、user-aware evaluation 四类新 benchmark，还明确判断“暂不深读”，并把热点用途限定为方向感维护。 |
| 官方文档或视频笔记 | 缺失 | 本周没有新增 `OpenAI Agent Evals`、`MCP Specification` 或 `Stanford CS25` 的正式笔记；辅助材料尚未转化为对 benchmark / eval 的理解补充。 |
| 最小实验 / 复现计划 | 缺失 | `experiments/` 本周没有新增或更新；目标文件 `experiments/2026-06-week-04-agentbench-vs-mcpmark-plan.md` 仍不存在，说明 `AgentBench` vs `MCPMark` 的固定字段对比还没有落盘。 |
| 周复盘 | 部分完成 | 本 reviewer 记录补上了外部检查、缺口和建议；但学习者自己的独立周复盘仍未形成，所以只能算部分完成，不能替代主观判断沉淀。 |

## 最有价值的判断

本周最有价值的判断来自 `radar/2026-06-week-04-hot-papers.md`：近期 agent benchmark 的增量越来越集中在真实工具环境、长程交互、轨迹诊断和用户感知错误四类维度。这个判断支持当前主线问题，即 `success rate` 已不足以解释 agent benchmark 的证据强弱。

更关键的 reviewer 判断是：现在最缺的依然不是新材料，而是把已有材料压成正式证据链。只要 `AgentBench` 深读、研究问题卡和最小实验计划还没落盘，就不应该再向 memory、browser 或 coding agent 扩主题。

## 最大缺口

最大缺口仍然是第 3 周收口所需三件套没有落盘：

1. `notes/2026-06-week-04-agentbench-reading-note.md`
2. `notes/2026-06-week-04-research-question-benchmark-verification-vs-trajectory.md`
3. `experiments/2026-06-week-04-agentbench-vs-mcpmark-plan.md`

这三个文件缺失时，仓库还无法判断 `AgentBench` 与 `MCPMark` 的 benchmark 结论到底主要受任务环境、verification 粒度，还是 trajectory-level diagnosis 影响。

## 需要降载还是推进

建议：继续降载，不推进到第 4 周阶段小结。

依据：

- 本周只完成热点 radar，仍未达到每周 Definition of Done。
- 第 4 周阶段 survey 需要第 3 周实验拆解作为证据底座；现在底座仍缺。
- 连续三次 reviewer 都指向同一问题：方向感已经有了，但正式产物闭环没有形成。

## 下周建议主题

下周主题继续保持不变：

> 用 `AgentBench` 作为旧 agent benchmark 基线，用 `MCPMark` 作为真实 MCP 工具环境 benchmark 对照，判断 verification 与 trajectory diagnosis 是否是新一代 agent benchmark 的主要增量。

## 建议阅读材料类型

- 1 篇深读 benchmark 论文：`AgentBench: Evaluating LLMs as Agents`
- 1 份官方 eval 文档：`OpenAI Agent Evals`
- 1 份协议边界材料：`Model Context Protocol 2025-06-18 Specification`

如果时间不足，官方文档和协议材料只做摘录式补充，不再扩新论文。

## 建议最小实验

实验目标：把 `AgentBench` 与 `MCPMark` 抽成一张固定字段对比表，判断真实 MCP 工具环境新增的评测难点是什么。

最小设计：

- 输入：两篇论文的 experiment / evaluation / limitation 相关章节
- 字段：任务环境、工具空间、baseline 类型、metric / verification、trajectory 记录、failure mode
- 输出：1 张对比表 + 1 段 150-300 字判断
- 边界：不写代码，不扩第三篇 benchmark，不做完整复现

## 降载补救计划

如果下周时间仍然有限，只做下面三件事：

1. 1 篇深读论文：`notes/2026-06-week-04-agentbench-reading-note.md`
2. 1 张研究问题卡：`notes/2026-06-week-04-research-question-benchmark-verification-vs-trajectory.md`
3. 1 个最小实验设计：`experiments/2026-06-week-04-agentbench-vs-mcpmark-plan.md`

完成这三件之前，不新增第 4 周 survey，不新增热点深读，不切换到 memory、browser、scientific agents 或 coding agents。

## Reviewer 建议

- `radar/2026-06-week-04-hot-papers.md` 已经足够维持方向感，下周不要再扩 radar。
- 优先把 `AgentBench` 深读写成正式笔记；如果只能完成一个文件，就完成它。
- 研究问题卡不要写成泛泛问题，必须落到“verification 粒度是否改变 benchmark 结论解释力”。
- 最小实验只做对比表和判断，不做代码实现；当前真正要训练的是实验拆解和证据边界判断。
