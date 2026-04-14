# 资源清单与阅读顺序

原则：优先一手资料；YouTube 负责帮助理解；Reddit 负责看工程经验，不负责定结论。

## 第一优先级：前 12 周必须反复看

### 官方

- [OpenAI Agents SDK](https://developers.openai.com/api/docs/guides/agents-sdk)
- [OpenAI Agent Evals](https://developers.openai.com/api/docs/guides/agent-evals)
- [OpenAI Docs MCP](https://developers.openai.com/learn/docs-mcp)
- [Model Context Protocol](https://github.com/modelcontextprotocol)

### 框架与工程

- [Anthropic: Building Effective AI Agents](https://resources.anthropic.com/hubfs/Building%20Effective%20AI%20Agents-%20Architecture%20Patterns%20and%20Implementation%20Frameworks.pdf?hsLang=en)
- [PydanticAI](https://github.com/pydantic/pydantic-ai)
- [LangGraph Docs](https://langchain-ai.github.io/langgraphjs/reference/modules/langgraph.html)
- [LlamaIndex](https://github.com/run-llama/llama_index)
- [Phoenix Observability](https://github.com/Arize-ai/phoenix)

## 第二优先级：第 13-20 周重点进入

### 协议与多智能体

- [Google Agent Protocols Guide](https://developers.googleblog.com/en/developers-guide-to-ai-agent-protocols/)
- [A2A Official Spec](https://google-a2a.github.io/A2A/latest/)

### Prompt 编程与前沿框架

- [DSPy](https://github.com/stanfordnlp/dspy)

## 第三优先级：用来建立研究判断力

### Benchmarks

- [SWE-bench](https://www.swebench.com/)
- [GAIA Leaderboard](https://huggingface.co/gaia-benchmark)
- [OSWorld](https://os-world.github.io/)

### 代表性项目

- [Browser Use](https://github.com/browser-use/browser-use)
- [OpenHands](https://github.com/OpenHands/OpenHands)
- [Agent-S](https://github.com/simular-ai/Agent-S)

## 推荐阅读顺序

### 第 1 阶段

- OpenAI Agents SDK
- Anthropic agent 文档
- PydanticAI

### 第 2 阶段

- LangGraph
- Phoenix
- LlamaIndex

### 第 3 阶段

- MCP
- A2A
- benchmark 页面与 paper

## YouTube 使用方法

只把 YouTube 当作“帮你更快理解”的渠道，别把它当 source of truth。

### 可以看什么

- benchmark 解读
- agent 架构对比
- 实战项目 walkthrough

### 不要怎么用

- 不要因为某个视频 demo 很炫就切主线
- 不要把“新框架发布”当成学习优先级
- 不要跳过官方文档直接抄视频代码

## Reddit / 社区的正确打开方式

适合看这些：

- 生产里踩过什么坑
- 为什么某框架被弃用或替换
- 哪些模式在真实场景会失控

不适合看这些：

- “哪个框架最强”式口水战
- 单条 anecdote 推导行业结论

## 你读资料时要写下来的问题

每次阅读至少回答下面 5 个问题：

- 这个东西解决什么问题
- 它的最小接口是什么
- 它和已有方案相比换来了什么
- 它引入了什么复杂度
- 什么情况下不该用它

