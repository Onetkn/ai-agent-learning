# Learning Dashboard

这个文件是仓库的学习入口。每周先看这里，再进入 `planning/current-week.md` 执行。

## 当前状态

- 当前定位：LLM / Agent 科研学习陪伴系统。
- 主线：科研阅读、问题意识、最小复现、阶段 survey。
- 辅线：工程能力只服务于验证论文判断，不追求完整产品化。
- 当前周次：第 1 周，从科研学习系统启动开始计数。

## 本周主题

建立 LLM / Agent 科研学习方法：学会读论文结构、记录问题、搭建自己的研究问题卡。

## 本周必须产出

- 1 篇完整论文阅读笔记。
- 1 张研究问题卡。
- 1 条热点论文 radar 记录。
- 1 份官方文档或课程笔记。
- 1 份周末复盘。

## 本周资源组合

| 类型 | 资源 | 用法 |
| --- | --- | --- |
| 论文基础 | [The Rise and Potential of Large Language Model Based Agents: A Survey](https://arxiv.org/abs/2309.07864) | 建立 agent 研究版图的第一层认知 |
| 路线图论文 | [A Review of Prominent Paradigms for LLM-Based Agents](https://aclanthology.org/2025.coling-main.652/) | 对 tool use、planning、RAG、feedback learning 做初步分类 |
| 热点速览 | [Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://openreview.net/forum?id=DT7JyQC3MR) | 只速览 abstract、problem setting 和 benchmark 设计 |
| 官方文档 | [Google ML Crash Course: Large language models](https://developers.google.com/machine-learning/crash-course/llm) | 补 LLM 基础概念：tokens、Transformer、训练与推理 |
| 工程文章 | [Anthropic: Building Effective AI Agents](https://www.anthropic.com/research/building-effective-agents) | 建立 workflow vs agent 的工程边界直觉 |
| 课程/视频 | [Stanford CS25](https://web.stanford.edu/class/cs25/past/cs25-v5/) | 作为背景课程入口，不要求本周完整看完 |

## 活跃研究问题

- 一篇 LLM/Agent 论文的贡献到底属于方法、系统、benchmark、数据还是分析？
- workflow 和 agent 的边界应该如何判断，而不是只看项目是否用了 LLM？
- 热点 agent 论文里的 benchmark 是否真的测到了研究声称的能力？

## 本周最小任务

本周不急着做工程代码，先把科研学习系统启动起来：

- 用 `templates/paper-reading-note.md` 深读 1 篇 agent survey。
- 用 `templates/research-question-card.md` 写 1 张问题卡。
- 用 `templates/hot-paper-radar.md` 速览 1-2 篇近期热点论文。
- 用 `templates/official-doc-note.md` 或 `templates/video-note.md` 记录 1 个非论文材料。
- 周末用 `templates/weekly-review.md` 复盘本周是否真正形成问题意识。

## 长期 Backlog

- 建立 `radar/` 周度热点论文记录。
- 为每个阶段写一份 mini survey。
- 选择一个最终研究问题：tool-use eval、agent memory eval、RAG faithfulness、或 coding/browser agent benchmark。
- 形成一个公开作品：复现报告、benchmark 再分析或小型 survey。

## 每周操作顺序

1. 打开 `planning/current-week.md`。
2. 完成深读论文和辅助材料。
3. 用模板写笔记、问题卡和热点 radar。
4. 周末运行复盘，把完成情况更新回本文件。
