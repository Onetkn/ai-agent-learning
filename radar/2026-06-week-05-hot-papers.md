# 2026-06 Week 05 Hot Paper Radar

更新日期：2026-06-29

## 本周判断目标

这周的 radar 只服务一个问题：

> 在 `AgentBench` 与 `MCPMark` 还没完成正式对比之前，哪些近 3-6 个月热点 benchmark 值得保留视野，但不应该抢走第 3 周收口任务？

## 热点速览

| 日期 | 方向 | 论文 | 来源 | 为什么这周值得看 | 是否立刻深读 | 下一步 |
| --- | --- | --- | --- | --- | --- | --- |
| 2026-06-29 | Agent tool use / MCP benchmarks | [LiveMCPBench: Can Agents Navigate an Ocean of MCP Tools?](https://openreview.net/forum?id=0sPCSssY2r&noteId=0qq1HrLsq6) | OpenReview；页面显示关注大规模 MCP 工具环境；会议状态未确认 | 适合补看“工具数量增长后，检索、选择、参数构造如何一起退化”，能和 `MCPMark` 的真实工具压力形成对照 | 暂不深读 | 只记录它强调的 tool discovery / large-scale tool selection 维度，等 `AgentBench` vs `MCPMark` 对比完成后再决定是否纳入 MCP benchmark 组 |
| 2026-06-29 | Agent memory and long-horizon interaction | [AMA-Bench: Evaluating Long-Horizon Memory for Agentic Applications](https://arxiv.org/abs/2602.22769) | arXiv，2026-02-26；代码与基准状态可继续追踪；会议状态未确认 | 它把 memory 从“对话回忆”推进到真实 agentic trajectory，提醒后续 memory 主题不能只看 QA accuracy | 暂不深读 | 作为第 15 周 memory 主题候选，先保留“causality + tool-augmented retrieval”这一判断线索 |
| 2026-06-29 | Agent memory and long-horizon interaction | [MemGym: a Long-Horizon Memory Environment for LLM Agents](https://arxiv.org/html/2605.20833v1) | arXiv，2026-05；会议状态未确认 | 它把 tool-use dialogue、deep research、coding、computer use 放进统一 memory-reasoning 接口，适合后续比较“跨任务 memory eval”而不是单场景 benchmark | 暂不深读 | 仅记录它的多轨评测框架，等阶段 1 闭环完成后再判断是否与 AMA-Bench 对读 |
| 2026-06-29 | Coding agents and SWE-style benchmarks | [SWE-EVO: Benchmarking Coding Agents in Long-Horizon Software Evolution](https://openreview.net/forum?id=SCpCfeSLtn) | OpenReview，约 3 个月内公开；会议状态未确认 | 它强调多文件、长时程软件演化，而不是单 bug 修复，能提醒后续 coding-agent 方向不要只盯 `SWE-bench` 成功率 | 暂不深读 | 先作为第 19-20 周 coding-agent 候选，不在本周扩成新深读债务 |

## 本周共性判断

- 最近 3-6 个月的热点 benchmark 正在从“单一成功率”转向“真实工具规模、长时程交互、跨轨迹记忆、软件演化”这些更贴近真实 agent 工作流的维度。
- 这些新 benchmark 的共同增量不是单纯换任务名，而是把 failure diagnosis 前移到了 tool selection、memory maintenance、trajectory continuity、long-horizon coordination。
- 这恰好支持当前主线的一个判断：只看 endpoint success rate 不足以解释 agent 为什么失败。
- 但本仓库现在缺的仍然是 `AgentBench` 深读、研究问题卡和最小实验计划；因此这些热点只进入 radar，不进入本周深读 backlog。

## 本周结论

- 本周不换主线，仍停留在 24 周路线图阶段 1 第 3 周收口。
- 新热点只用于丰富后续选题空间，不用于扩大本周任务。
- 当前最小且正确的推进顺序仍然是：
  1. 完成 `AgentBench` 深读笔记
  2. 完成 `OpenAI Agent Evals` 或 `Stanford CS25` 笔记
  3. 完成 `AgentBench` vs `MCPMark` 最小对比实验
  4. 再决定是否进入第 4 周阶段小结
