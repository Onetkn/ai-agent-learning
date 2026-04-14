# 实验：zero-shot vs few-shot 对结构化抽取稳定性的影响

日期：2026-04-14  
阶段：第 1 周  
目标：用一个最小实验理解 few-shot 什么时候真的有帮助

## 1. 问题定义

要验证的问题：

- 在同一个信息抽取任务里，few-shot 是否比 zero-shot 更稳定？
- 它提升的是准确率、格式稳定性，还是只是让输出更长？

为什么重要：

- 第 2 周你要做结构化抽取器
- 如果你现在不先理解 zero-shot 和 few-shot 的差别，后面会很容易靠“加样例”硬堆 prompt

## 2. 任务设计

任务：从一段客服留言中抽取 4 个字段

- `customer_name`
- `product`
- `issue_type`
- `urgency`

输出要求：

- 只输出 JSON
- 缺失字段输出 `null`
- 不要猜测没有明确出现的信息

## 3. 样本数据

### 样本 1

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

### 样本 2

```text
我刚收到净水器 FilterMax 2，包装有点压坏，但机器目前看起来能用，不着急。
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

### 样本 3

```text
我是王婷，订单里的 CoffeeGo 胶囊机漏水，今天已经第三次了，希望你们马上联系我。
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

## 4. zero-shot 版本

```text
你是一个结构化信息抽取助手。

任务：从用户留言中抽取 customer_name、product、issue_type、urgency 四个字段。

规则：
- 只抽取文本中明确出现的信息
- 缺失字段输出 null
- urgency 只能是 high、medium、low
- 只输出 JSON，不要输出解释

用户留言：
{{input}}
```

## 5. few-shot 版本

```text
你是一个结构化信息抽取助手。

任务：从用户留言中抽取 customer_name、product、issue_type、urgency 四个字段。

规则：
- 只抽取文本中明确出现的信息
- 缺失字段输出 null
- urgency 只能是 high、medium、low
- 只输出 JSON，不要输出解释

示例 1
输入：
我是张磊，昨天买的 LightBook 阅读灯不亮了，后天要送人，请尽快帮我处理。

输出：
{
  "customer_name": "张磊",
  "product": "LightBook 阅读灯",
  "issue_type": "不亮",
  "urgency": "high"
}

示例 2
输入：
收到 FreshCup 保温杯了，杯身有划痕，不过还能用，不着急。

输出：
{
  "customer_name": null,
  "product": "FreshCup 保温杯",
  "issue_type": "杯身划痕",
  "urgency": "low"
}

用户留言：
{{input}}
```

## 6. 如何执行

### 方式 A：直接在聊天界面里做

步骤：

1. 复制 zero-shot prompt。
2. 把 3 条样本分别代入 `{{input}}`。
3. 记录输出结果。
4. 再用 few-shot prompt 重复一遍。
5. 对比格式稳定性和字段准确性。

### 方式 B：用 API 做

如果你后面有 `OPENAI_API_KEY`，可以用下面命令自己跑。  
为什么跑这个命令：它是最小化的文本调用，能让你只关注 prompt 差异，不被额外工程细节干扰。

```bash
curl https://api.openai.com/v1/responses \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-4o",
    "input": "你是一个结构化信息抽取助手。任务：从用户留言中抽取 customer_name、product、issue_type、urgency 四个字段。规则：只抽取文本中明确出现的信息；缺失字段输出 null；urgency 只能是 high、medium、low；只输出 JSON，不要输出解释。用户留言：你好，我是李明。上周买的 AirBuds Pro 右耳突然没声音了，明天要出差，麻烦尽快处理。"
  }'
```

注意：

- 不要把 API Key 写进仓库
- 用环境变量传入
- 第 1 周不用急着写脚本，先手动比对也完全够用

## 7. 记录模板

| 版本 | 样本 | 是否字段正确 | 是否严格 JSON | 是否猜测缺失信息 | 备注 |
| --- | --- | --- | --- | --- | --- |
| zero-shot | 样本 1 |  |  |  |  |
| zero-shot | 样本 2 |  |  |  |  |
| zero-shot | 样本 3 |  |  |  |  |
| few-shot | 样本 1 |  |  |  |  |
| few-shot | 样本 2 |  |  |  |  |
| few-shot | 样本 3 |  |  |  |  |

## 8. 你要重点观察什么

- few-shot 是否减少了“输出解释文字”的情况
- few-shot 是否更少猜测 `customer_name`
- few-shot 是否让 `urgency` 标签更稳定
- few-shot 的额外 token 成本是否值得

## 9. 预期结论

大多数情况下，你大概率会看到：

- zero-shot 已经能完成简单抽取
- few-shot 会让格式更稳，标签边界更清楚
- 但 few-shot 也会让 prompt 更长、成本更高

所以这一周最重要的不是得出“few-shot 一定更强”，而是理解：

- 什么时候 zero-shot 已经够用
- 什么时候 few-shot 的额外成本是值得的

## 10. 做完后写一句结论

请补一行你自己的结论：

```text
在这个任务里，我认为 few-shot / zero-shot 更值得作为默认起点，因为：
```
