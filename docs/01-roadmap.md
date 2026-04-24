# 24 周 LLM / Agent 科研学习路线图

这条路线以“科研研究为主导，工程能力为辅助”为原则。核心目标不是快速做出一个 agent demo，而是能系统阅读论文、识别研究 gap、复现实验、提出可验证问题，并用最小工程原型验证判断。

## 总体节奏

- 每周读 2 篇深读论文：1 篇经典/基础，1 篇当前路线相关。
- 每周速览 2-4 篇热点论文：只判断是否值得后续深读或复现。
- 每周沉淀 1 张研究问题卡。
- 每 4 周完成 1 次阶段 survey 或小复现总结。

## 阶段 1：研究入门与论文阅读方法（第 1-4 周）

目标：从“看懂概念”升级为“能拆论文、找问题、写 related work”。

### 第 1 周

- 学 LLM/Agent 论文的基本结构：abstract、introduction、method、experiment、limitation。
- 建立论文阅读笔记和研究问题卡格式。
- 输出：
  - 一篇论文阅读笔记
  - 一张研究问题卡
  - 一个术语表：agent、tool use、planning、RAG、eval、benchmark

### 第 2 周

- 学如何判断论文贡献：新问题、新方法、新 benchmark、新分析还是系统整合。
- 对比 2 篇相近论文的 problem setting 和 evaluation setting。
- 输出：
  - 一篇 related work 对比笔记
  - 一个“贡献类型”判断表
  - 一个最小可复现实验设想

### 第 3 周

- 学如何读实验：dataset、baseline、metric、ablation、failure case。
- 选择一篇 agent/tool-use 论文拆解实验设计。
- 输出：
  - 实验设置拆解笔记
  - 3 个可能的复现风险
  - 1 个可缩小规模的复现方案

### 第 4 周

- 学如何从论文中提出研究问题。
- 写阶段 survey：LLM/Agent 当前有哪些核心问题还没解决。
- 输出：
  - 阶段 survey
  - 3 张候选研究问题卡
  - 一篇“工程实现能验证什么、不能验证什么”的说明

## 阶段 2：Tool Use、Planning 与 Agent Workflow（第 5-8 周）

目标：理解 agent 的核心能力边界：什么时候需要工具、什么时候需要规划、什么时候只是 workflow。

### 第 5 周

- 读 tool use / function calling / API grounding 相关论文。
- 关注问题：工具选择、参数构造、错误恢复、工具过多时的退化。
- 输出：
  - tool use 论文笔记
  - 工具调用失败类型表
  - 一个最小工具选择实验

### 第 6 周

- 读 planning / ReAct / plan-and-execute 相关论文。
- 关注问题：计划是否真的提升成功率，还是只增加 token 和错误传播。
- 输出：
  - planning 方法对比笔记
  - 固定 workflow vs agent planning 对比实验设计
  - 一张 planning 研究问题卡

### 第 7 周

- 读 research agent 或 tool-augmented reasoning 相关论文。
- 做一个最小研究助理原型，只验证引用、事实抽取和步骤控制。
- 输出：
  - 最小 research agent 复现记录
  - 失败案例 3 条
  - 一份“agent 子步骤是否可控”的分析

### 第 8 周

- 做阶段 survey：tool use、planning、workflow 的边界。
- 总结哪些任务不需要 agent，哪些任务必须让模型动态决策。
- 输出：
  - 阶段 survey
  - 一份 agent workflow taxonomy
  - 一个可继续深入的研究问题

## 阶段 3：RAG、Long-Context 与 Retrieval Evaluation（第 9-12 周）

目标：理解知识增强不是“加向量库”，而是检索、上下文、引用和评测之间的系统取舍。

### 第 9 周

- 读 RAG 基础论文和现代 retrieval pipeline 论文。
- 关注问题：什么时候 RAG 优于直接 long-context。
- 输出：
  - RAG 核心机制笔记
  - RAG vs long-context 问题卡
  - 一个小型检索数据集设想

### 第 10 周

- 读 rerank、hybrid retrieval、query rewrite 相关论文。
- 关注问题：提升召回是否会损害 faithfulness 或 latency。
- 输出：
  - retrieval 改进方法对比
  - 2 个 retrieval ablation 方案
  - 失败案例分类

### 第 11 周

- 读 RAG eval、citation、faithfulness 相关论文。
- 做一个最小 RAG 评测实验。
- 输出：
  - RAG eval 指标笔记
  - baseline / rerank / query rewrite 小实验
  - 实验报告草稿

### 第 12 周

- 做阶段 survey：RAG、long-context 与 retrieval eval 的证据链。
- 输出：
  - 阶段 survey
  - 一个可复用的 RAG eval checklist
  - 一个后续研究问题

## 阶段 4：Agent Evaluation、Reliability、Memory 与 Benchmark（第 13-16 周）

目标：把关注点从“系统能跑”转向“能力如何被可靠测量”。

### 第 13 周

- 读 agent evaluation survey 或 benchmark 论文。
- 关注问题：success rate、trajectory quality、tool correctness、human preference 各自测什么。
- 输出：
  - agent eval 指标表
  - benchmark 适用边界分析
  - 一张 eval 研究问题卡

### 第 14 周

- 读 reliability、abstention、hallucination、uncertainty 相关论文。
- 关注问题：模型什么时候应该拒答或请求更多信息。
- 输出：
  - reliability 论文笔记
  - 失败类型与指标映射
  - 一个小型拒答/不确定性测试集

### 第 15 周

- 读 agent memory、long-horizon interaction 相关论文。
- 关注问题：memory 是提升能力，还是引入污染和错误检索。
- 输出：
  - memory agent 论文笔记
  - memory failure case taxonomy
  - 一个最小 memory eval 设想

### 第 16 周

- 读 MCP/tool-use benchmark 或真实工具环境 benchmark 论文。
- 关注问题：标准化工具协议如何改变 agent 评测。
- 输出：
  - MCP/tool benchmark 笔记
  - 工具选择与参数构造错误分析
  - 阶段 survey

## 阶段 5：热点追踪专题（第 17-20 周）

目标：主动追热点，但用研究问题和证据筛选热点，不追产品新闻或营销叙事。

### 第 17-18 周

- 从热点 radar 中选择方向 A，默认优先：
  - MCP/tool-use benchmark
  - agent memory and long-horizon interaction
  - agent evaluation and reliability
  - research/scientific agents
- 输出：
  - 5-8 篇热点速览表
  - 2 篇深读笔记
  - 1 个小复现或 benchmark 再分析

### 第 19-20 周

- 选择方向 B，默认优先：
  - coding agents and SWE-style benchmarks
  - browser/computer-use agents
  - RAG vs long-context / retrieval evaluation
  - multi-agent coordination and protocol design
- 输出：
  - 5-8 篇热点速览表
  - 2 篇深读笔记
  - 方向 A/B 对比报告

## 阶段 6：研究问题收束与作品化（第 21-24 周）

目标：选择一个可验证研究问题，形成小规模研究闭环。

### 第 21 周

- 从前 20 周的问题卡中筛选 1 个主问题。
- 写清楚：研究背景、gap、为什么重要、可验证假设。
- 输出：
  - 研究问题说明
  - related work 初稿
  - 最小实验设计

### 第 22 周

- 完成小复现或小规模 benchmark 再分析。
- 输出：
  - 复现记录
  - 数据/样本说明
  - 初步结果表

### 第 23 周

- 做 ablation、失败案例分析或指标敏感性分析。
- 输出：
  - ablation 报告
  - failure analysis
  - 研究结论边界

### 第 24 周

- 完成一个公开作品：survey、复现报告、benchmark 分析或小研究报告。
- 输出：
  - 完整研究报告
  - 可复现实验说明
  - 后续研究方向

## 24 周后你应该达到的状态

- 能读懂 LLM/Agent 论文的核心贡献和证据强弱。
- 能把热点论文放进已有研究脉络里，而不是只看标题新不新。
- 能提出一个可验证的小研究问题。
- 能用最小工程实验复现或挑战论文结论。
- 能写出结构清晰的 related work、实验分析和阶段 survey。
