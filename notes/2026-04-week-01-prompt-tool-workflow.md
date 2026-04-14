# 第 1 周笔记：prompt、tool、workflow 的区别

更新时间：2026-04-14

## 这周只学什么

第 1 周先只吃透 4 个主题：

- `system prompt` / `developer instruction`
- few-shot
- token / cost
- context window

先别扩展到 agent、RAG、LangChain。这个阶段的目标不是“知道很多名词”，而是把最基础的控制杆摸清楚。

## 推荐学习顺序

### 第一层：先看官方

- OpenAI Prompt engineering  
  https://developers.openai.com/api/docs/guides/prompt-engineering
- OpenAI Reasoning best practices  
  https://developers.openai.com/api/docs/guides/reasoning-best-practices
- OpenAI Key concepts  
  https://developers.openai.com/api/docs/concepts
- OpenAI Pricing  
  https://developers.openai.com/api/docs/pricing
- Anthropic Prompt engineering overview  
  https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview
- Anthropic Long context prompting  
  https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices#long-context-prompting

### 第二层：再看视频辅助理解

- OpenAI Academy: Introduction to Prompt Engineering  
  https://academy.openai.com/public/videos/introduction-to-prompt-engineering-2025-02-13
- B 站：ChatGPT 提示工程课程（吴恩达 & OpenAI）  
  https://www.bilibili.com/video/BV15P411i7eQ
- B 站：OpenAI 提示工程最佳实践  
  https://www.bilibili.com/video/BV1Hz4y1w7dZ/

我的使用原则是：

- 官方文档负责定义概念和边界。
- 视频负责帮你更快理解。
- B 站负责中文辅助，不负责当最终依据。

## prompt、tool、workflow 到底有什么区别

| 概念 | 它是什么 | 解决的问题 | 什么时候用 | 容易误解的地方 |
| --- | --- | --- | --- | --- |
| prompt | 你给模型的指令、上下文、约束、示例 | 控制模型“怎么回答” | 单轮或多轮生成、分类、抽取、改写 | 它不是业务流程，更不是系统架构 |
| tool | 模型可以调用的外部能力 | 让模型获取训练外信息，或执行动作 | 查天气、查数据库、发请求、写文件 | 工具不是“模型自己会了”，而是系统给它开了接口 |
| workflow | 一组稳定、可重复的步骤编排 | 把任务拆成可控流程 | ETL、审核流、先抽取再校验 | workflow 不一定需要模型，更不一定需要 agent |

一句话版本：

- `prompt` 决定模型怎么想、怎么说。
- `tool` 决定模型能查什么、做什么。
- `workflow` 决定系统按什么顺序推进。

## `system prompt` / `developer instruction` 是什么

在新的 OpenAI API 文档里，更常见的是 `developer` 消息，而不是老说法里的 `system prompt`。OpenAI 在 prompt engineering 文档中把 `developer` 消息定义为高优先级指令，优先级高于 `user` 消息；你可以把它理解成“应用写死的规则和业务逻辑”。  
参考：OpenAI Prompt engineering，2026-04-14 查验。

我的理解：

- `developer instruction` 用来规定助手身份、边界、输出要求、调用工具规则。
- `user prompt` 用来给当前任务输入。
- 如果两者冲突，通常以更高优先级的开发者指令为准。

适合放在 `developer instruction` 里的内容：

- 角色和目标
- 输出格式要求
- 工具使用规则
- 安全边界
- 成功标准

不适合放在里面的内容：

- 每次都变化的业务输入
- 超长原始材料
- 和本次任务无关的背景碎片

## 什么是 few-shot，什么时候该用

OpenAI 的 prompt engineering 文档把 few-shot 定义成：通过在 prompt 里放少量输入/输出示例，让模型学到你想要的模式，而不是去做 fine-tuning。文档还明确建议：示例要覆盖有代表性的输入，且和你的指令保持一致。  
参考：OpenAI Prompt engineering，2026-04-14 查验。

我的实战理解：

- zero-shot：只有任务说明，没有样例。
- one-shot：给 1 个样例。
- few-shot：给几个高质量样例。

few-shot 最适合的场景：

- 你想固定输出风格
- 你想约束分类标签
- 你想让模型学会特定抽取格式
- 单靠一句指令不够稳定

few-shot 不等于“例子越多越好”：

- 例子越多，token 成本越高。
- 例子越多，可能把模型注意力拖偏。
- 例子如果风格不一致，会让模型更混乱。
- 对 reasoning 模型，官方现在更建议先试 zero-shot，再在必要时补 few-shot。

## prompt 的基础结构

结合 OpenAI 和 Anthropic 文档，一个稳妥的 prompt 通常有这几层：

1. 身份
2. 任务目标
3. 约束条件
4. 输出格式
5. 示例
6. 上下文材料

OpenAI 的 prompt engineering 文档还专门建议：用 Markdown 标题、列表、XML 标签来标清逻辑边界；典型的开发者消息可以分成 `Identity`、`Instructions`、`Examples`、`Context` 四段。  
参考：OpenAI Prompt engineering，2026-04-14 查验。

一个最小骨架：

```text
# Identity
你是一个信息抽取助手。

# Instructions
- 只抽取输入中明确出现的事实
- 缺失字段输出 null
- 不要补充猜测

# Output format
返回 JSON，对应给定 schema。

# Examples
输入 A -> 输出 A

# Context
这里放本次任务需要的额外资料
```

## token、cost、context window 应该怎么理解

### 1. token 是什么

OpenAI 在 Key concepts 文档里把 token 定义为文本处理的基本分块。一个粗略经验值是：英文 1 token 大约是 4 个字符，或者 0.75 个单词。更重要的是，输入 token 和输出 token 都会影响使用成本。  
参考：OpenAI Key concepts，2026-04-14 查验。

你现在只需要记住：

- token 不是“字数”
- 中文、英文、标点、空格的切分都不一样
- 长 prompt、长上下文、长输出都会涨成本

### 2. context window 是什么

OpenAI 在 Key concepts 文档里提醒：对于生成模型，prompt 和输出加起来，不能超过模型最大上下文长度。也就是说，context window 不是“只算输入”，而是整个对话上下文预算。  
参考：OpenAI Key concepts，2026-04-14 查验。

所以 context window 更像：

- 一个总预算
- 输入材料、历史消息、工具结果、输出内容都在里面抢空间

这也是为什么“上下文窗口越大越好”并不准确：

- 大窗口通常更贵，或至少更容易让你不节制地塞材料
- 材料变长后，结构不清楚会让质量下降
- 能塞进去，不等于模型一定能稳定抓住重点

### 3. 成本受什么影响

OpenAI Pricing 页面当前明确区分了：

- input token
- cached input token
- output token
- built-in tool 调用费用

例如，Pricing 页面在 2026-04-14 查验时明确列出了 built-in tools 的单独计费，例如 `Web search`、`File search`、`Tool call` 都有额外费用。不同模型的输入、缓存输入、输出价格也不同。  
参考：OpenAI Pricing，2026-04-14 查验。

因此你算成本时，至少要看 4 件事：

- 用的是哪个模型
- 输入有多长
- 输出有多长
- 有没有调用工具

## 长上下文时怎么放材料

Anthropic 的文档对长上下文有两个很实用的建议：

- 长文档和长输入尽量放在 prompt 靠前位置
- 用户真正的问题放在后面

它还建议用 XML 标签给文档分段，并且要求模型先引用相关段落，再执行任务。这个思路对长材料问答、合同审阅、多文档比对都很有用。  
参考：Anthropic Long context prompting，2026-04-14 查验。

一个简单模板：

```xml
<documents>
  <document index="1">
    <source>policy.md</source>
    <document_content>
    ...
    </document_content>
  </document>
</documents>

<task>
先引用最相关的原文，再回答问题。
</task>
```

## 这一周最重要的 6 个判断

1. prompt 是控制模型行为，不是替代系统设计。
2. `developer instruction` 负责规则，`user input` 负责当前任务。
3. few-shot 的核心是“样例质量和一致性”，不是“数量”。
4. context window 是总预算，不是纯输入上限。
5. 成本不只看模型单价，还要看输出长度和工具调用。
6. 长上下文任务最怕的不是材料不够，而是材料没有结构。

## 本周建议交付

- 一篇笔记：就是这篇，重点理解概念边界。
- 一份术语表：见 `2026-04-week-01-glossary.md`。
- 一个最小实验：见 `experiments/2026-04-week-01-zero-shot-vs-few-shot.md`。

## 自测题

- 你能不能用自己的话解释 `prompt`、`tool`、`workflow` 的区别？
- 你能不能说明为什么 few-shot 不是越多越好？
- 你能不能解释为什么超长聊天历史会把成本拉高？
- 你能不能解释为什么长上下文里“材料摆放顺序”会影响效果？
- 你能不能说出哪些内容该放进 `developer instruction`，哪些不该放？
