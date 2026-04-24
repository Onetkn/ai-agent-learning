# LLM / Agent 领域地图

这份地图用于防止学习路线漏项。每周计划都应该映射到其中 1-2 个领域，避免资料很多但能力树没有增长。

## 1. LLM 基础

要学什么：

- tokenization
- Transformer
- pretraining
- instruction tuning
- RLHF / RLAIF
- reasoning
- inference、latency、cost

关键问题：

- 模型能力来自训练、上下文、工具还是后处理？
- reasoning 模型和普通生成模型的差异如何被评测？
- 成本、延迟和质量如何取舍？

推荐材料类型：

- Google ML Crash Course LLM 模块
- Stanford CS25 / CS336
- 经典 LLM survey
- 模型报告和技术报告

## 2. Prompt 与结构化输出

要学什么：

- prompt patterns
- few-shot / zero-shot
- JSON schema
- structured outputs
- function calling
- tool calling
- retry / validation

关键问题：

- 哪些任务只需要 prompt + schema，不需要 agent？
- 结构化输出失败时，问题来自 prompt、schema 还是任务定义？
- tool description 如何影响工具选择？

推荐材料类型：

- OpenAI structured output / tool calling 文档
- Pydantic 文档
- 工具调用相关论文
- 本仓库结构化抽取器实验

## 3. Agent 架构

要学什么：

- workflow vs agent
- ReAct
- planning
- reflection
- tool loop
- stop condition
- multi-agent

关键问题：

- 什么时候 agent 比固定 workflow 更值得？
- planning 是否真实提高成功率，还是只增加成本？
- multi-agent 是能力提升还是复杂度转移？

推荐材料类型：

- Anthropic Building Effective AI Agents
- AgentBench
- LLM agent survey
- LangGraph / PydanticAI 文档

## 4. RAG 与知识系统

要学什么：

- chunking
- embedding
- vector store
- hybrid retrieval
- rerank
- query rewrite
- long-context
- citation
- faithfulness

关键问题：

- RAG 什么时候优于 long-context？
- rerank 提升召回时是否损害引用忠实度？
- citation correctness 和 answer correctness 是否一致？

推荐材料类型：

- DeepLearning.AI RAG 课程
- LlamaIndex / LangGraph RAG 示例
- RAG eval 论文
- 本地小型 benchmark

## 5. Evaluation

要学什么：

- LLM eval
- RAG eval
- agent trajectory eval
- benchmark design
- LLM-as-judge
- human preference
- regression eval

关键问题：

- benchmark 实际测到什么，没测到什么？
- LLM-as-judge 是否稳定、公平、可复现？
- agent 的成功率是否掩盖了错误轨迹？

推荐材料类型：

- OpenAI Agent Evals
- AgentBench
- SWE-bench / GAIA / OSWorld
- eval survey 和 benchmark paper

## 6. Memory

要学什么：

- short-term memory
- long-term memory
- episodic memory
- semantic memory
- memory retrieval
- memory write policy
- memory eval
- memory pollution / forgetting

关键问题：

- memory 是真实能力提升，还是更好的 retrieval？
- 长期记忆如何避免过时、矛盾和隐私风险？
- memory benchmark 是否能代表真实长期任务？

推荐材料类型：

- MemoryAgentBench
- MemAgents workshop
- memory survey
- 长期交互 benchmark

## 7. Coding / Browser / Computer-Use Agents

要学什么：

- SWE-style benchmark
- repository navigation
- patch generation
- browser use
- GUI grounding
- OSWorld
- trace analysis

关键问题：

- coding agent 失败来自理解需求、定位代码还是验证不足？
- browser/GUI agent 的环境变化如何影响评测？
- 轨迹日志比最终答案多提供了什么证据？

推荐材料类型：

- SWE-bench
- OSWorld
- Browser Use / OpenHands / Agent-S
- coding agent benchmark
- 真实 PR / CI 调试记录

## 8. Protocols 与工程生态

要学什么：

- MCP
- A2A
- OpenAI Agents SDK
- LangGraph
- PydanticAI
- LlamaIndex
- observability
- tracing

关键问题：

- 协议解决的是连接问题、评测问题还是治理问题？
- 框架抽象隐藏了哪些 failure mode？
- tracing 如何服务科研分析，而不是只服务 debug？

推荐材料类型：

- MCP 官方规范
- OpenAI Agents SDK
- framework docs
- MCP/tool-use benchmark

## 9. Safety / Reliability

要学什么：

- guardrails
- permissions
- prompt injection
- tool abuse
- abstention
- uncertainty
- sandbox
- budget / max steps

关键问题：

- agent 在什么情况下应该停下或请求确认？
- 工具权限如何影响 benchmark 与真实使用？
- 安全机制会不会降低任务成功率？

推荐材料类型：

- safety benchmark
- prompt injection 论文
- OpenAI / Anthropic 安全文档
- 工具权限设计案例

## 10. Research Methods

要学什么：

- paper reading
- related work
- research question
- reproduction
- ablation
- survey
- failure analysis
- writing

关键问题：

- 如何从一篇论文提炼出可验证问题？
- 如何判断实验设置是否支撑结论？
- 如何把工程实验写成科研报告？

推荐材料类型：

- 论文笔记模板
- 研究问题卡
- 复现计划
- 阶段 survey
