# 学习陪伴系统使用说明

这个仓库不只是路线图，而是一套每周运转的学习陪伴系统。它的目标是让你每周都知道：学什么、为什么学、看哪些资料、做什么验证、留下什么产物。

## 系统由什么组成

| 模块 | 文件或目录 | 作用 |
| --- | --- | --- |
| 总入口 | `LEARNING_DASHBOARD.md` | 看当前周主题、资源、研究问题和 backlog |
| 路线图 | `docs/01-roadmap.md` | 决定 24 周的大方向 |
| 领域地图 | `docs/05-field-map.md` | 防止漏掉 LLM/Agent 关键领域 |
| 资源规则 | `docs/06-resource-playbook.md` | 决定论文、官方文档、视频、社区内容怎么用 |
| 每周计划 | `planning/current-week.md` | 本周真正执行的任务清单 |
| 热点雷达 | `radar/` | 保存每周热点论文和方向判断 |
| 产物模板 | `templates/` | 统一论文笔记、视频笔记、复现计划和复盘格式 |

## 每周怎么用

### 周一：定方向

- 先看 `LEARNING_DASHBOARD.md`。
- 再看 `planning/current-week.md`。
- 确认本周只回答 1 个研究问题。
- 材料必须混合：论文 + 官方文档或 benchmark + 视频/课程或代码仓库。

### 周中：做学习闭环

- 深读论文时用 `templates/paper-reading-note.md`。
- 看官方文档时用 `templates/official-doc-note.md`。
- 看 YouTube/B站课程时用 `templates/video-note.md`。
- 看到热点论文时用 `templates/hot-paper-radar.md` 先速览，不急着全读。
- 工程验证用 `templates/reproduction-plan.md` 控制范围。

### 周末：复盘和降噪

- 用 `templates/weekly-review.md` 做复盘。
- 更新研究问题卡：保留、缩小、放弃或转入 backlog。
- 如果本周没有完成深读，不补堆资料；下周降载，只保留 1 篇论文 + 1 个问题卡。

## 资料之间怎么配合

- 论文负责建立研究判断：问题是否重要、证据是否充分、实验是否可信。
- 官方文档负责确认接口和边界：API、协议、框架能力、eval 工作流。
- 视频/课程负责降低理解成本：先看懂大图景，再回论文。
- 代码仓库/benchmark 负责验证：看真实数据、任务定义、失败模式。
- 社区讨论负责找踩坑线索：只当经验，不当结论。

## 什么叫一次合格学习

一次合格学习不是“看完一堆资料”，而是留下可以复用的判断：

- 我知道这个方向在解决什么问题。
- 我知道至少 2 种方法的差异。
- 我知道一个 benchmark 或 metric 的局限。
- 我能提出一个可验证的问题。
- 我知道下一步应该读什么或做什么实验。

## 自动化怎么参与

- `weekly-learning-planner`：每周生成或更新当前周计划、dashboard 和学习材料组合。
- `weekly-learning-reviewer`：每周末检查产物，指出薄弱点，并给出下周降载或推进建议。

自动化可以帮你选材和整理节奏，但最终判断要写进笔记和问题卡里。这个仓库的核心资产不是链接，而是你的研究判断。
