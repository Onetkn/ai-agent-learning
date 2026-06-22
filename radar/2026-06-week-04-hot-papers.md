# 2026-06 Week 04 Hot Paper Radar

更新日期：2026-06-22

## 本周判断目标

这周的 radar 只服务一个问题：

> 在 `AgentBench` 与 `MCPMark` 还没有完成正式对比之前，哪些近 3-6 个月热点 benchmark 值得保留视野，但不应该抢走第 3 周闭环任务？

## 热点速览

| 日期 | 方向 | 论文 | 来源 | 为什么这周值得看 | 是否立刻深读 | 下一步 |
| --- | --- | --- | --- | --- | --- | --- |
| 2026-06-22 | Agent tool use / MCP benchmarks | [MCP-Bench: Benchmarking Tool-Using LLM Agents with Complex Real-World Tasks via MCP Servers](https://openreview.net/forum?id=fe8mzHwMxN) | OpenReview，约 8 个月前发布；会议状态未确认 | 摘要强调 28 个 MCP server、250 个工具、多步真实任务、跨工具协调和参数控制，正好补足 `MCPMark` 之外的 MCP benchmark 形态 | 暂不深读 | 只记录它的评测维度；等 `AgentBench` vs `MCPMark` 表格完成后，再判断是否加入 MCP benchmark 对照组 |
| 2026-06-22 | Agent memory and long-horizon interaction | [AMemGym: Interactive Memory Benchmarking for Assistants in Long-Horizon Interactions](https://openreview.net/forum?id=sfrVLzsmlf) | OpenReview，约 4 个月前发布；会议状态未确认 | 它批评静态 off-policy memory benchmark，并提出 interactive / on-policy 评测环境，和当前“endpoint accuracy 是否足够”问题高度相关 | 暂不深读 | 作为第 15 周 memory 主题候选，不提前扩成本周深读 |
| 2026-06-22 | Browser / computer-use agents | [Benchmarking MCP Tool Invocation In Computer-Use Agents](https://openreview.net/forum?id=rceD6wwt4B) | OpenReview；会议状态未确认 | 它把 MCP tool invocation、GUI operation、decision-making 放进同一真实环境，适合后续比较“工具调用”和“界面操作”两类错误来源 | 暂不深读 | 只保留为 browser / computer-use agent 支线线索 |
| 2026-06-22 | Agent evaluation and reliability | [User-aware Agent Evaluation with Automated Error Analysis](https://openreview.net/forum?id=fHsVNklKOc) | OpenReview，约 4 个月前发布；会议状态未确认 | 摘要强调自动错误分析和 user expertise 维度，能提醒本仓库后续不要只看平均 success rate，而要看错误是否对不同用户同样严重 | 暂不深读 | 后续若进入 agent eval 主题，可和 `OpenAI Agent Evals` 的 traces / graders 对照 |

## 本周共性判断

- 近期 agent benchmark 的增量越来越集中在“真实工具环境、长程交互、轨迹诊断、用户感知错误”四类维度。
- 这些论文都能支持当前主线的一个判断：`success rate` 本身不足以解释 agent 为什么失败。
- 但本仓库现在还缺的是 `AgentBench` 深读、研究问题卡和最小实验计划；因此这些热点只进入 radar，不进入深读 backlog。

## 本周结论

- 本周不换主线，仍停留在 24 周路线图第 1 阶段第 3 周收口。
- 新热点只用于丰富后续选题空间，不用于扩大本周任务。
- 当前最小且正确的推进顺序仍然是：
  1. 完成 `AgentBench` 深读笔记
  2. 完成 `OpenAI Agent Evals` 或 `Stanford CS25` 笔记
  3. 完成 `AgentBench` vs `MCPMark` 最小对比实验
  4. 再决定是否进入第 4 周阶段小结
