# Current Week Plan

周次：第 3 周

日期：2026-04-24 起

主研究主题：如何读懂 LLM/Agent 论文里的实验设计

## 本周能力目标

- 能拆解一篇 agent 论文的 dataset、baseline、metric、ablation 和 failure case。
- 能把论文 claim 转成一个可验证假设。
- 能把已有结构化抽取器材料改造成微型 eval。

## 本周深读论文

| 轨道 | 论文 | 为什么读 |
| --- | --- | --- |
| 基础/路线图 | [A Review of Prominent Paradigms for LLM-Based Agents](https://aclanthology.org/2025.coling-main.652/) | 建立 agent 研究问题分类，理解 tool use、planning、RAG、feedback learning 的关系 |
| 热点/实验拆解 | [Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://openreview.net/forum?id=DT7JyQC3MR) | 练习读 benchmark 设计、metric 和 long-horizon agent evaluation |

## 热点速览

| 方向 | 资源 | 判断任务 |
| --- | --- | --- |
| Agent benchmark | [AgentBench](https://openreview.net/forum?id=zAdUB0aCTQ) | 判断它测的是通用 agent 能力还是环境适配能力 |
| MCP/tool-use eval | [ICLR Blogposts: General Agent Evaluation](https://iclr-blogposts.github.io/2026/blog/2026/general-agent-evaluation/) | 观察 MCP 是否正在变成 eval 环境标准 |
| RAG eval | [DeepLearning.AI Advanced RAG](https://www.deeplearning.ai/alpha/short-courses/building-evaluating-advanced-rag/) | 提炼 RAG triad 与论文 metric 的关系 |

## 官方文档 / 课程补充

- [OpenAI Agent Evals](https://platform.openai.com/docs/guides/agent-evals)：看 eval workflow 和 agent trajectory 评测思路。
- [Anthropic: Building Effective AI Agents](https://www.anthropic.com/research/building-effective-agents)：对照 workflow vs agent 的工程边界。
- [Stanford CS25](https://web.stanford.edu/class/cs25/past/cs25-v5/)：补 agent reasoning 与现代 LLM 背景。

## 本周最小实验

把已有 `experiments/2026-04-week-02-structured-extractor-samples.md` 升级为微型 eval 设计。

- baseline：固定 prompt + 固定 schema。
- variant：加入错误分类和 retry 规则。
- metric：schema parse rate、关键字段准确率、失败类型分布。
- 输出：`experiments/2026-04-week-03-structured-extractor-eval-plan.md`。

## 本周研究问题卡

建议问题：

> 对结构化输出任务来说，错误主要来自模型理解失败、schema 设计不清，还是缺少 retry/eval 机制？

输出位置：

- `notes/2026-04-week-03-research-question-structured-eval.md`

## 周末复盘 Checklist

- [ ] 是否完成至少 1 篇深读论文笔记？
- [ ] 是否写下 1 张研究问题卡？
- [ ] 是否记录热点 radar？
- [ ] 是否完成微型 eval 设计？
- [ ] 是否明确下周继续、缩小还是换题？
