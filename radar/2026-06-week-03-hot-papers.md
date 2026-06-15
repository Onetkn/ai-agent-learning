# 2026-06 Week 03 Hot Paper Radar

更新日期：2026-06-16

## 本周判断目标

这周的 radar 继续只服务一个问题：

> 当第 3 周 benchmark / eval 闭环还没完成时，哪些近 3-6 个月热点论文值得保留在视野里，但不应该立刻扩成新的深读 backlog？

## 热点速览

| 日期 | 方向 | 论文 | 来源 | 为什么这周值得看 | 是否立刻深读 | 下一步 |
| --- | --- | --- | --- | --- | --- | --- |
| 2026-06-16 | Research agents / scientific discovery | [AstaBench: Rigorous Benchmarking of AI Agents with a Scientific Research Suite](https://openreview.net/forum?id=M7TNf5J26u) | OpenReview，2026-01-26 发布，ICLR 2026 Oral | 它把 scientific research agent 评测从单任务 demo 提升到 2400+ 问题、可复现实验环境和多类基线，适合后续接到 research-agent 主线 | 暂不深读 | 先记住它强调“受控工具环境 + 产品化任务覆盖”，等 benchmark 主线闭环后再比较它与 `AgentBench` / `MCPMark` 的证据粒度 |
| 2026-06-16 | Coding / research code agents | [RECODE-H: A Benchmark for Research Code Development with Interactive Human Feedback](https://openreview.net/forum?id=IKnuyyPHCV) | OpenReview，2026-01-26 发布，ICLR 2026 Poster | 它不是普通 SWE-style benchmark，而是把研究代码实现放进多轮反馈和单元测试回路，更接近“科研助理 agent”真实协作形态 | 暂不深读 | 如果后续扩 coding-agent 方向，优先比较它的 feedback hierarchy 与 `SWE-bench` 这类终局指标的差异 |
| 2026-06-16 | MCP safety / reliability | [MCP-SafetyBench: A Benchmark for Safety Evaluation of Large Language Models with Real-World MCP Servers](https://openreview.net/forum?id=7XYjeL46co) | OpenReview，2026-01-26 发布，ICLR 2026 Poster | 它把 MCP benchmark 从“能不能完成任务”扩展到“真实多服务器工作流里会怎样失稳”，很适合作为 `MCPMark` 后续的 reliability 分支 | 暂不深读 | 闭环完成后，优先和 `MCPMark` 做“能力评测 vs 安全评测”的 benchmark 设计对照 |
| 2026-06-16 | Agent memory | [Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://openreview.net/forum?id=DT7JyQC3MR) | OpenReview，2026-01-26 发布，ICLR 2026 Poster | 它把 memory 明确拆成 retrieval、test-time learning、long-range understanding、selective forgetting 四类能力，说明 agent eval 正从 endpoint accuracy 走向 competency-level diagnosis | 暂不深读 | 后续可观察它与 benchmark failure analysis 的共通诊断维度，再决定是否进入 memory 主线 |

## 本周共性判断

- 2026 年上半年的热点 benchmark 已明显从单一 success rate 走向更细粒度的验证、诊断、反馈与安全性。
- research-agent、research-code-agent、MCP safety、memory 四条线都在加强“可解释失败分析”，这和当前仓库主线高度相关。
- 但对本仓库现在最重要的不是再扩新方向，而是先把 `AgentBench` 与 `MCPMark` 的 benchmark 判断写实。

## 本周结论

- 本周不换主线，仍停留在 24 周路线图第 1 阶段第 3 周收口。
- 热点跟踪的作用是保留后续选题方向，而不是抢走当前深读与最小实验的时间。
- 当前最小且正确的推进顺序仍然是：
  1. 完成 `AgentBench` 深读笔记
  2. 完成 `OpenAI Agent Evals` 或 `Stanford CS25` 笔记
  3. 完成 `AgentBench` vs `MCPMark` 最小对比实验
  4. 再决定是否进入第 4 周阶段小结
