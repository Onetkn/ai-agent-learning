# 第 2 周实验：结构化抽取器测试样本与失败案例

更新日期：2026-04-20

## 实验目标

为 Project 01 先准备一套最小但可复用的验证资产，覆盖：

- 10 条测试样本
- 3 条失败案例
- 一致的字段定义

本文件不假设具体模型、SDK 或脚本入口，先把“评什么”固定下来。

## 字段约定

目标字段：

- `customer_name`
- `product`
- `issue_type`
- `urgency`

约束：

- 缺失字段输出 `null`
- 不允许编造姓名、产品名或问题类型
- `urgency` 只允许 `high`、`medium`、`low`

## 10 条测试样本

### 样本 01

输入：

```text
你好，我是李明。上周买的 AirBuds Pro 右耳突然没声音了，明天要出差，麻烦尽快处理。
```

期望输出：

```json
{
  "customer_name": "李明",
  "product": "AirBuds Pro",
  "issue_type": "右耳无声",
  "urgency": "high"
}
```

### 样本 02

输入：

```text
刚收到净水器 FilterMax 2，包装角有明显压损，不过机器看起来还能用，不着急。
```

期望输出：

```json
{
  "customer_name": null,
  "product": "FilterMax 2",
  "issue_type": "包装破损",
  "urgency": "low"
}
```

### 样本 03

输入：

```text
我是王婷，订单里的 CoffeeGo 胶囊机一直漏水，今天已经第三次了，希望今天联系我。
```

期望输出：

```json
{
  "customer_name": "王婷",
  "product": "CoffeeGo 胶囊机",
  "issue_type": "漏水",
  "urgency": "high"
}
```

### 样本 04

输入：

```text
晨光阅读灯 LightBook 开不了机，孩子这周上课要用，最好这两天给答复。
```

期望输出：

```json
{
  "customer_name": null,
  "product": "LightBook",
  "issue_type": "无法开机",
  "urgency": "medium"
}
```

### 样本 05

输入：

```text
张蕾反馈 SmartKettle 水壶底部有轻微渗水，但暂时还能使用，不急。
```

期望输出：

```json
{
  "customer_name": "张蕾",
  "product": "SmartKettle",
  "issue_type": "底部渗水",
  "urgency": "low"
}
```

### 样本 06

输入：

```text
订单里的 SleepCare 加湿器噪音特别大，晚上完全没法睡，麻烦尽快处理。
```

期望输出：

```json
{
  "customer_name": null,
  "product": "SleepCare 加湿器",
  "issue_type": "噪音过大",
  "urgency": "high"
}
```

### 样本 07

输入：

```text
我是陈峰，昨天收到 FitBand 4，屏幕有一道划痕，希望帮我确认能不能换货。
```

期望输出：

```json
{
  "customer_name": "陈峰",
  "product": "FitBand 4",
  "issue_type": "屏幕划痕",
  "urgency": "medium"
}
```

### 样本 08

输入：

```text
你好，HomeBake 烤面包机左侧按钮按下去没反应，不过我下周才搬家，暂时不着急。
```

期望输出：

```json
{
  "customer_name": null,
  "product": "HomeBake 烤面包机",
  "issue_type": "按钮失灵",
  "urgency": "low"
}
```

### 样本 09

输入：

```text
刘洋的 PureSound Mini 音箱无法配对蓝牙，今天活动现场就要用，越快越好。
```

期望输出：

```json
{
  "customer_name": "刘洋",
  "product": "PureSound Mini",
  "issue_type": "蓝牙无法配对",
  "urgency": "high"
}
```

### 样本 10

输入：

```text
AirClean S 的滤芯仓盖子合不上，已经试了两次，麻烦这周内回复一下。
```

期望输出：

```json
{
  "customer_name": null,
  "product": "AirClean S",
  "issue_type": "滤芯仓盖无法闭合",
  "urgency": "medium"
}
```

## 3 条失败案例

### 失败案例 01：姓名被模型猜测

输入：

```text
昨天买的 BrewCup Pro 漏液了，请尽快联系。
```

错误倾向：

- 模型可能凭语气编造 `customer_name`

正确期望：

```json
{
  "customer_name": null,
  "product": "BrewCup Pro",
  "issue_type": "漏液",
  "urgency": "high"
}
```

失败原因标记建议：

- `hallucinated_missing_field`

### 失败案例 02：urgency 枚举不稳定

输入：

```text
净水壶 AquaLite 的出水速度有点慢，暂时还能接受。
```

错误倾向：

- 模型可能输出 `normal`、`not_urgent` 之类的非枚举值

正确期望：

```json
{
  "customer_name": null,
  "product": "AquaLite",
  "issue_type": "出水缓慢",
  "urgency": "low"
}
```

失败原因标记建议：

- `invalid_enum_value`

### 失败案例 03：把投诉语气误当问题类型

输入：

```text
我是赵欣，这个 RoboClean M1 真让人头疼，昨天到货后一直启动不了。
```

错误倾向：

- 模型可能把“真让人头疼”抽成 `issue_type`

正确期望：

```json
{
  "customer_name": "赵欣",
  "product": "RoboClean M1",
  "issue_type": "无法启动",
  "urgency": "medium"
}
```

失败原因标记建议：

- `semantic_span_misalignment`

## 这套样本现在能做什么

- 手动对比 zero-shot / few-shot
- 后续接入 Pydantic 校验
- 给重试策略提供失败分类
- 作为项目代码落地前的共同验收基线
