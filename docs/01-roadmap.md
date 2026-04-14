# 24 周 AI Agent / 大模型学习路线图

这条路线以“应用工程为主，研究视角加持”为原则。核心目标是：你能从零设计、实现、评测并解释一个 agent 系统，而不是只会调用几个框架 demo。

## 阶段 1：基础打底（第 1-4 周）

目标：把“会调模型”升级成“会设计系统”。

### 第 1 周

- 学 `system prompt`、few-shot、token/cost、上下文窗口
- 学结构化输出与 JSON schema 的意义
- 输出：
  - 一篇笔记：`prompt`、`tool`、`workflow` 的区别
  - 一个术语表：context window、temperature、schema、retry

### 第 2 周

- 学 Python async、HTTP API、Pydantic、日志
- 做项目 1：结构化抽取器
- 输出：
  - 输入/输出 schema
  - 10 条测试样本
  - 失败案例 3 条

### 第 3 周

- 学 tool calling、函数签名、参数校验、重试
- 做项目 2：FAQ/工具助手
- 输出：
  - 至少 2-3 个工具
  - 清晰的工具描述与错误返回

### 第 4 周

- 学 agent 基元：`observe -> think -> act -> verify -> stop`
- 补齐 Docker、环境管理、基础日志
- 输出：
  - 阶段总结
  - “为什么多数任务不需要 multi-agent”的解释稿

## 阶段 2：单智能体与工作流（第 5-8 周）

目标：先把单 agent 做稳。

### 第 5 周

- 学 ReAct、tool loop、stop condition
- 区分 workflow 和 agent
- 输出：
  - 一个对比表：固定流程 vs 开放问题

### 第 6 周

- 学 timeout、fallback、error handling
- 给现有助手加：
  - 最大步数
  - 超时控制
  - 重试策略

### 第 7 周

- 做项目 3：研究助理 agent
- 要求：
  - 能搜索网页或本地资料
  - 能抽取事实
  - 能给出引用
  - 子步骤数量受控

### 第 8 周

- 建立失败分类：
  - 幻觉
  - 工具选错
  - 循环
  - 无效检索
  - 格式崩坏
- 输出：
  - 一份失败分析报告

## 阶段 3：RAG 与评测（第 9-12 周）

目标：把“会检索”升级成“能证明效果”。

### 第 9 周

- 学 chunking、embedding、metadata、vector store
- 搭最朴素 RAG

### 第 10 周

- 学 rerank、hybrid retrieval、citation
- 为 RAG 增加：
  - metadata filter
  - 引用输出
  - 召回结果检查

### 第 11 周

- 做项目 4：私有知识库问答系统
- 至少比较 3 个版本：
  - baseline RAG
  - rerank RAG
  - query rewrite 或 agentic RAG

### 第 12 周

- 学 RAG eval：
  - answer relevance
  - retrieval relevance
  - faithfulness
  - latency
  - cost
- 输出：
  - 一份实验报告
  - 一份版本对比结论

## 阶段 4：MCP、生产化与安全（第 13-16 周）

目标：进入真正的 agent engineering。

### 第 13 周

- 学 MCP 中的 tools、resources、client/server 边界
- 解释为什么标准化协议比手写 glue code 更适合长期维护

### 第 14 周

- 做项目 5：自定义 MCP server
- 要求：
  - 暴露 2-3 个工具
  - 暴露 1 个资源
  - 有清晰 schema、错误返回和权限说明

### 第 15 周

- 学 tracing、graders、regression eval
- 为已有 agent 增加：
  - 基本 tracing
  - 失败类型统计
  - 样本回放

### 第 16 周

- 加 guardrails：
  - 工具白名单
  - 参数校验
  - 敏感操作确认
  - budget
  - max steps
  - timeout
- 输出：
  - 一个带人工审核节点的 workflow

## 阶段 5：前沿增强（第 17-20 周）

目标：接触前沿，但仍以“可解释、可比较”为准。

四选二即可：

- coding agents
- computer-use / browser agents
- multi-agent
- DSPy / programmatic prompting

### 第 17-18 周

- 选方向 A，做最小可运行实验
- 输出：
  - 为什么它优于单 agent
  - 它增加了什么成本和复杂度

### 第 19-20 周

- 选方向 B，做最小可运行实验
- 输出：
  - 适用场景
  - 不适用场景
  - 与方向 A 的对比

## 阶段 6：研究视角与作品集（第 21-24 周）

目标：形成“工程 + 研究”的闭环。

### 第 21 周

- 读一个 agent 工程文档并复盘
- 推荐优先：OpenAI Agents SDK 或 Anthropic agent 文档

### 第 22 周

- 读一个 benchmark 并复盘
- 推荐优先：SWE-bench、GAIA、OSWorld 三选一

### 第 23 周

- 读一个框架设计思路并复盘
- 推荐优先：LangGraph、PydanticAI、DSPy 三选一

### 第 24 周

- 完成 1 个公开作品
- 写一篇长文：
  - 单 agent
  - plan-and-execute
  - supervisor multi-agent
  - DSPy 优化
  - 各自优劣与边界

## 24 周后你应该达到的状态

- 能独立做一个带工具调用的 agent
- 能解释为什么某任务该用 workflow、agent、RAG 或 multi-agent
- 能做基础评测，而不是只凭感觉调 prompt
- 能理解 MCP 的价值，并写出最小 server
- 能读 benchmark，不把榜单当广告海报看

