# Learning Dashboard

这个文件是仓库的学习入口。每周先看这里，再进入 `planning/current-week.md` 执行。

## 当前状态

- 当前定位：LLM / Agent 科研学习陪伴系统。
- 主线：科研阅读、问题意识、最小复现、阶段 survey。
- 辅线：工程能力只服务于验证论文判断，不追求完整产品化。
- 当前推断周次：第 3 周，基于仓库已有 `week-01` 和 `week-02` 笔记与实验材料。

## 本周主题

读懂 LLM/Agent 论文里的实验设计：dataset、baseline、metric、ablation、failure case。

## 本周必须产出

- 1 篇完整论文阅读笔记。
- 1 张研究问题卡。
- 1 条热点论文 radar 记录。
- 1 个最小复现或实验设计。
- 1 份周末复盘。

## 本周资源组合

| 类型 | 资源 | 用法 |
| --- | --- | --- |
| 论文基础 | [A Review of Prominent Paradigms for LLM-Based Agents](https://aclanthology.org/2025.coling-main.652/) | 建立 agent 研究方向分类 |
| 前沿论文 | [Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://openreview.net/forum?id=DT7JyQC3MR) | 练习拆 benchmark 和实验设置 |
| 官方文档 | [OpenAI Agent Evals](https://platform.openai.com/docs/guides/agent-evals) | 对照论文 metric 与实际 eval 工作流 |
| 工程文章 | [Anthropic: Building Effective AI Agents](https://www.anthropic.com/research/building-effective-agents) | 理解 workflow vs agent 的工程边界 |
| 课程/视频 | [Stanford CS25](https://web.stanford.edu/class/cs25/past/cs25-v5/) | 补 LLM/agent 背景和研究脉络 |

## 活跃研究问题

- Agent benchmark 到底测的是模型能力、工具描述理解，还是环境适配能力？
- 当工具数量增加时，失败主要来自工具选择、参数构造，还是停止条件？
- Memory agent 的长期交互评测是否能迁移到真实 research assistant 场景？

## 本周最小实验

从已有结构化抽取器材料出发，把 10 条测试样本改造成一个微型 eval：

- baseline：固定 prompt + 固定 schema。
- variant：加入错误分类和 retry 规则。
- metric：schema parse rate、关键字段准确率、失败类型分布。
- 目标：练习把工程结果写成论文式实验记录。

## 长期 Backlog

- 建立 `radar/` 周度热点论文记录。
- 为每个阶段写一份 mini survey。
- 选择一个最终研究问题：tool-use eval、agent memory eval、RAG faithfulness、或 coding/browser agent benchmark。
- 形成一个公开作品：复现报告、benchmark 再分析或小型 survey。

## 每周操作顺序

1. 打开 `planning/current-week.md`。
2. 完成深读论文和辅助材料。
3. 用模板写笔记、问题卡和实验计划。
4. 周末运行复盘，把完成情况更新回本文件。
