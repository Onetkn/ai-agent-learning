# Week 02：Structured Extractor Schema

更新日期：2026-04-20

## 目标

为 Project 01 提供一份独立、可审阅的输入/输出约束文档，先固定边界，再决定后续代码实现。

## 输入 schema

输入对象最小形态：

```json
{
  "ticket_text": "string"
}
```

约束说明：

- `ticket_text` 必填
- 输入只接受单条原始文本
- 本周不额外假设订单号、渠道、时间戳等元数据

## 输出 schema

```json
{
  "customer_name": "string | null",
  "product": "string | null",
  "issue_type": "string | null",
  "urgency": "high | medium | low | null"
}
```

字段解释：

- `customer_name`
  仅在文本中明确出现姓名时填写
- `product`
  仅抽取文本中明确提到的产品名
- `issue_type`
  用简短名词短语概括问题
- `urgency`
  依据原文紧急程度映射到固定枚举

## 抽取规则

- 只抽取文本中明确出现的信息
- 未出现的信息必须返回 `null`
- 不把情绪词、抱怨词直接当作问题类型
- 不输出 schema 外字段
- 不输出解释性文字

## urgency 映射原则

- `high`
  出现“尽快”“马上”“今天要用”“明天出差”等强时效表达
- `medium`
  出现“这周内”“最好尽快”“希望尽早回复”等中等时效表达
- `low`
  明确表示“不着急”“还能用”“暂时可接受”

## 最小校验清单

- JSON 是否可解析
- 4 个字段是否全部存在
- `urgency` 是否落在允许枚举内
- 缺失信息是否使用 `null`
- 是否出现猜测字段

## 本周落地假设

当前仓库里还没有稳定的抽取脚本或模型接入代码，因此本周先把 schema 文档和测试资产固定下来，后续实现时再补：

- Pydantic 模型
- API 调用层
- 日志与重试
