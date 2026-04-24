# Current Week Plan

周次：第 1 周

日期：2026-04-24 起

主研究主题：建立 LLM / Agent 科研学习方法

## 本周能力目标

- 能看懂一篇 LLM/Agent 论文的基本结构：abstract、introduction、method、experiment、limitation。
- 能判断论文贡献类型：方法、系统、benchmark、数据、分析或 survey。
- 能把阅读中的疑问写成一张可继续追踪的研究问题卡。
- 能区分论文、官方文档、视频课程和社区经验各自该怎么用。

## 本周深读论文

| 轨道 | 论文 | 为什么读 |
| --- | --- | --- |
| 基础/经典 | [The Rise and Potential of Large Language Model Based Agents: A Survey](https://arxiv.org/abs/2309.07864) | 先建立 LLM agent 的整体版图，避免一开始被单个框架或热点带偏 |
| 路线图相关 | [A Review of Prominent Paradigms for LLM-Based Agents](https://aclanthology.org/2025.coling-main.652/) | 用一篇较新的 survey 练习分类 tool use、planning、RAG 和 feedback learning |

## 热点速览

| 方向 | 资源 | 判断任务 |
| --- | --- | --- |
| Agent memory | [Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions](https://openreview.net/forum?id=DT7JyQC3MR) | 只看 abstract、problem setting、benchmark 目标，判断它为什么是近期热点 |
| Agent benchmark | [AgentBench](https://openreview.net/forum?id=zAdUB0aCTQ) | 速览 benchmark 由哪些环境组成，先不做完整复现 |

## 官方文档 / 课程补充

- [Google ML Crash Course: Large language models](https://developers.google.com/machine-learning/crash-course/llm)：补 LLM 基础概念。
- [Anthropic: Building Effective AI Agents](https://www.anthropic.com/research/building-effective-agents)：建立 workflow vs agent 的工程边界直觉。
- [Stanford CS25](https://web.stanford.edu/class/cs25/past/cs25-v5/)：作为背景课程入口，本周只选 1 个相关 talk 或课程页面速览。

## 本周最小任务

本周先搭学习闭环，不急着做工程复现。

- 论文笔记：用 `templates/paper-reading-note.md` 记录 1 篇深读论文。
- 问题卡：用 `templates/research-question-card.md` 写 1 张研究问题卡。
- 热点 radar：用 `templates/hot-paper-radar.md` 记录 1-2 篇热点速览。
- 非论文材料：用 `templates/official-doc-note.md` 或 `templates/video-note.md` 记录 1 个官方文档/课程材料。

## 本周研究问题卡

建议问题：

> 对 LLM/Agent 入门学习来说，如何判断一篇论文的贡献是“真正的新研究问题”，还是已有问题的新包装？

输出位置：

- `notes/2026-04-week-01-research-question-paper-contribution.md`

## 周末复盘 Checklist

- [ ] 是否完成至少 1 篇深读论文笔记？
- [ ] 是否写下 1 张研究问题卡？
- [ ] 是否记录热点 radar？
- [ ] 是否完成 1 份官方文档或视频笔记？
- [ ] 是否明确第 2 周要继续补基础，还是进入实验设计拆解？
