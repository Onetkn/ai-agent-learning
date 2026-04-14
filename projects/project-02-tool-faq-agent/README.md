# Project 02: Tool FAQ Agent

## 目标

做一个能调用 2-3 个工具的小助手，重点练习：

- tool calling
- 参数校验
- stop condition
- error handling

## 推荐技术栈

- Python
- Pydantic
- OpenAI Agents SDK 或 PydanticAI

## 最小范围

- 2-3 个清晰工具
- 工具有参数 schema
- 有错误返回
- 有最大步数和超时

## 必做项

- 写清每个工具解决什么问题
- 记录 tool selection 失败案例
- 说明为什么这里需要 agent，而不是纯流程

## 完成标准

- 不会无限调用工具
- 参数错误时能被拦截
- 回答可复现、可调试

