# 资源使用 Playbook

学习 LLM/Agent 不能只读论文，也不能只看视频。这个 playbook 定义每类资源的作用、使用时机和产出要求。

## 资源分级

| 资源类型 | 主要作用 | 什么时候用 | 必须产出 |
| --- | --- | --- | --- |
| 论文 | 建立研究判断 | 定义问题、比较方法、判断证据 | 论文笔记或热点 radar |
| 官方文档 | 确认工程边界 | 查 API、协议、框架能力、eval 流程 | 官方文档笔记 |
| 课程 / YouTube / B站 | 快速建立直觉 | 进入新领域前、读论文卡住时 | 视频笔记 |
| 代码仓库 / benchmark | 做复现和失败分析 | 需要验证论文 claim 时 | 复现计划或实验报告 |
| 社区讨论 | 找踩坑线索 | 工程实现遇到模糊问题时 | 经验摘录，不作为结论 |

## 论文怎么用

论文用于回答：

- 这个方向的核心问题是什么？
- 这篇论文贡献了新方法、新系统、新 benchmark，还是新分析？
- 实验是否支撑结论？
- 哪个 claim 值得复现？

使用规则：

- 深读每周最多 2 篇。
- 热点速览每周 2-4 篇。
- 不能只收藏链接，必须写“是否值得继续”的判断。
- arXiv 论文必须额外检查代码、实验设置、作者、引用和会议状态。

## 官方文档怎么用

官方文档用于回答：

- 这个 API 或框架实际支持什么？
- 输入输出、错误处理、权限边界是什么？
- 它和论文里的抽象是否一致？

优先来源：

- [OpenAI Agents SDK](https://developers.openai.com/api/docs/guides/agents-sdk)
- [OpenAI Agent Evals](https://platform.openai.com/docs/guides/agent-evals)
- [Model Context Protocol](https://github.com/modelcontextprotocol)
- [PydanticAI](https://github.com/pydantic/pydantic-ai)
- [LangGraph](https://langchain-ai.github.io/langgraphjs/reference/modules/langgraph.html)
- [LlamaIndex](https://github.com/run-llama/llama_index)

使用规则：

- 官方文档只解决“怎么做”和“边界是什么”，不直接证明科研结论。
- 每次读文档都要写：它确认了哪个接口、限制或设计取舍。

## 课程 / YouTube / B站怎么用

课程和视频用于降低理解成本，不能替代论文。

优先来源：

- [Stanford CS25](https://web.stanford.edu/class/cs25/past/cs25-v5/)
- [Google ML Crash Course: LLMs](https://developers.google.com/machine-learning/crash-course/llm)
- [DeepLearning.AI RAG Course](https://www.deeplearning.ai/courses/retrieval-augmented-generation)
- 李宏毅生成式 AI / 大模型课程
- 高质量会议 talk、作者 talk、paper walkthrough

使用规则：

- 看视频前先写下想解决的问题。
- 看完只保留 3-5 条真正改变理解的点。
- 视频里的 claim 必须回到论文、官方文档或 benchmark 验证。
- B站内容优先选高校课程、作者讲解、会议 talk；少看标题党实战合集。

## 代码仓库 / Benchmark 怎么用

代码和 benchmark 用于把论文判断变成可验证实验。

优先来源：

- [SWE-bench](https://www.swebench.com/)
- [GAIA](https://huggingface.co/gaia-benchmark)
- [OSWorld](https://os-world.github.io/)
- [OpenHands](https://github.com/OpenHands/OpenHands)
- [Browser Use](https://github.com/browser-use/browser-use)
- [Phoenix Observability](https://github.com/Arize-ai/phoenix)

使用规则：

- 先读任务定义和 metric，再看 leaderboard。
- 先做 5-20 条样本的小复现，不追求完整复现。
- 必须记录失败案例，而不只记录最好结果。

## 社区讨论怎么用

社区讨论适合找真实问题：

- 哪些框架在生产里难用？
- 哪些 eval 指标被滥用？
- 哪些 agent failure 在论文里没被覆盖？

使用规则：

- Reddit、Hacker News、博客和中文社区只能当线索。
- 不把单个经验当结论。
- 如果社区观点重要，必须找到论文、benchmark 或代码证据。

## 每周资源配方

默认每周组合：

- 2 篇深读论文。
- 2-4 篇热点速览论文。
- 1 个官方文档或 benchmark。
- 1 个视频/课程/talk。
- 1 个最小实验或复现计划。

忙碌周降载：

- 1 篇深读论文。
- 1 个官方文档。
- 1 张研究问题卡。
- 不新增工程任务。
