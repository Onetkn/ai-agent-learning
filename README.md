# LLM / Agent 科研学习工作区

这套仓库用于把大模型与 agent 学习从“会做 demo”推进到“能读论文、提出问题、复现实验、判断研究价值”。主线是科研阅读、问题意识和小规模实验验证；工程能力栈保留为辅助，用来复现论文观点、做 ablation、搭建最小可验证系统。

## 先看什么

1. 先看 [LEARNING_DASHBOARD.md](/D:/Learning/LEARNING_DASHBOARD.md)，确认本周学什么、为什么学、要留下什么产物。
2. 看 [docs/00-learning-system.md](/D:/Learning/docs/00-learning-system.md)，理解这个学习陪伴系统怎么运转。
3. 看 [docs/01-roadmap.md](/D:/Learning/docs/01-roadmap.md) 和 [docs/05-field-map.md](/D:/Learning/docs/05-field-map.md)，理解 24 周路线和 LLM/Agent 能力地图。
4. 看 [planning/current-week.md](/D:/Learning/planning/current-week.md)，开始执行本周计划。
5. 用 [docs/06-resource-playbook.md](/D:/Learning/docs/06-resource-playbook.md) 决定论文、官方文档、视频、代码仓库和社区资料怎么搭配。

## 仓库结构

```text
LEARNING_DASHBOARD.md  每周学习入口和状态看板
docs/          学习系统说明、路线图、领域地图、资源规则、每周推进方法
planning/      当前周计划和周计划模板
radar/         热点论文与方向速览
templates/     论文笔记、文档笔记、视频笔记、研究问题卡、复现计划、周复盘模板
notes/         论文阅读笔记、概念解释、related work 梳理
experiments/   论文复现、小规模 ablation、benchmark 对比记录
projects/      最小工程验证、研究原型、复现实验目录
reports/       阶段 survey、研究报告、复现总结、公开作品文稿
```

## 默认学习节奏

- 每周 6-8 小时。
- 论文阅读 40%，问题整理 20%，复现/实验 30%，复盘 10%。
- 每周默认读：
  - 1 篇经典/基础论文深读
  - 1 篇当前路线图相关论文深读
  - 2-4 篇热点前沿论文速览
- 每周默认还要看：
  - 1 个官方文档、benchmark 或代码仓库
  - 1 个课程、YouTube、B站或作者 talk
- 工程实现只做最小可复现，不追求产品化完整度。

## 当前研究主线

- LLM agent 的 tool use、planning、workflow 边界。
- RAG、long-context、retrieval evaluation 的取舍。
- Agent evaluation、reliability、memory、benchmark 设计。
- MCP/tool-use benchmark、coding/browser/computer-use agents 等热点方向。
- 最终目标是形成一个可解释、可复现、可扩展的小研究问题，而不是只完成一个应用项目。

## 本仓库的使用规则

- 每周至少留下 1 份论文笔记和 1 张研究问题卡。
- 每周计划必须同时包含论文、官方文档/benchmark、视频/课程和最小实验。
- 每个工程实验都必须回答：它验证了哪篇论文的哪个判断。
- 每个阶段至少完成 1 个小复现或 ablation。
- 每次引用结论，优先使用论文、官方 benchmark、代码仓库或开放评审记录。
- 如果一个方向无法回答“它解决了什么 gap、证据是否充分、还能怎么验证”，说明还没学透。

## 建议起步顺序

- 第 1 周：读路线图，建立论文阅读台账和研究问题卡。
- 第 1-4 周：学习如何读 LLM/Agent 论文、拆解实验、写 related work。
- 第 5 周起：围绕 tool use、planning、RAG、eval、memory 等方向持续做论文阅读和最小复现。
- 第 17 周起：进入热点追踪专题，每两周集中跟一个前沿方向。

## 当前已准备好的模板

- [每周学习计划模板](/D:/Learning/templates/weekly-learning-plan.md)
- [论文阅读笔记模板](/D:/Learning/templates/paper-reading-note.md)
- [研究问题卡模板](/D:/Learning/templates/research-question-card.md)
- [官方文档笔记模板](/D:/Learning/templates/official-doc-note.md)
- [视频/课程笔记模板](/D:/Learning/templates/video-note.md)
- [热点论文 Radar 模板](/D:/Learning/templates/hot-paper-radar.md)
- [复现/Ablation 计划模板](/D:/Learning/templates/reproduction-plan.md)
- [能力检查点模板](/D:/Learning/templates/capability-checkpoint.md)
- [学习日志模板](/D:/Learning/templates/daily-log.md)
- [实验报告模板](/D:/Learning/templates/experiment-report.md)
- [周复盘模板](/D:/Learning/templates/weekly-review.md)
