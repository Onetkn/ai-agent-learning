# Project 01: Structured Extractor

## 目标

把非结构化文本稳定抽取成结构化 JSON，重点练习：

- structured output
- schema 设计
- 输出校验
- 基础测试

## 推荐技术栈

- Python
- Pydantic
- 你当前最熟悉的模型 API

## 最小范围

- 输入一段文本
- 输出固定 schema 的 JSON
- 字段缺失时显式处理
- 至少 10 条测试样本

## 必做项

- 写清输入/输出 schema
- 保留失败案例
- 记录哪些字段最不稳定

## 完成标准

- 大多数字段能稳定产出
- 错误输出可以被拦截或修复
- 你能解释 schema 为什么这样设计

