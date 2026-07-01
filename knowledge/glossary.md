# Glossary

## 文件用途

持续维护 AI 产品与工程术语。定义以“能帮助自己继续学习、沟通和做产品判断”为准。

## 核心问题

- 我能否不用术语堆叠，用自己的话解释它？
- 它和相邻概念的边界是什么？
- 它在真实产品或代码中怎样出现？

| 术语 | 简明解释 | 继续理解 |
| --- | --- | --- |
| LLM | Large Language Model，大语言模型；能理解和生成语言、代码等内容。 | 训练、推理、Token 与能力边界 |
| Agent | 以目标为导向，能根据环境信息决定并执行下一步动作的 AI 系统。 | 自主程度、停止条件与可靠性 |
| Agent Loop | Agent 反复观察、判断、行动并接收反馈的运行闭环。 | 循环控制、恢复与可观测性 |
| Tool | Agent 可调用的具体外部能力，如搜索、读文件或执行命令。 | Schema、权限与错误处理 |
| Function Calling | 模型按定义好的函数名和参数结构发起调用，由宿主程序执行。 | 结构化输出与工具选择 |
| Skill | 为一类任务封装的可复用方法，常包含指令、步骤、资源或脚本。 | 与 Prompt、Tool、Workflow 的边界 |
| MCP | Model Context Protocol；让 AI 应用统一连接外部工具、资源和数据。 | Client / Server、传输与授权 |
| Context | 模型当前能看到的指令、对话、工具结果和资料。 | 窗口、相关性与压缩 |
| Memory | 系统跨轮次或任务保存和取回重要信息的机制。 | 写入、检索、遗忘与隐私 |
| RAG | Retrieval-Augmented Generation；先检索资料，再基于资料生成。 | 切分、召回、排序与引用 |
| Plan Mode | Agent 执行前先探索、拆分任务并形成可确认计划的模式。 | 启用时机、粒度与更新 |
| Multi-Agent | 多个 Agent 通过分工、协作或竞争共同完成任务。 | 委派、隔离、冲突与成本 |
| Prompt Engineering | 设计指令、上下文、示例和约束以提高模型任务效果。 | 稳定性、评测与模型差异 |
| Coding Agent | 能理解代码库、使用开发工具并完成软件工程任务的 Agent。 | 仓库理解、安全与验证 |
| CLI | Command-Line Interface，通过文本命令操作程序的界面。 | Shell、参数、管道与退出码 |
| SDK | Software Development Kit，使用某平台能力的一组库、工具和示例。 | 与 API 的关系、版本与抽象 |
| API | Application Programming Interface，软件之间交换请求和响应的接口。 | 协议、鉴权、限流与错误码 |

## 待补充术语

- [ ] Token
- [ ] Embedding
- [ ] Structured Output
- [ ] Guardrail
- [ ] Evals

## 学习记录

| 日期 | 新增 / 修订术语 | 原因 |
| --- | --- | --- |
| 待填写 | 待填写 | 待填写 |

## 后续更新方向

- 补充 Token、Embedding、Structured Output、Guardrail 和 Evals。
- 为重要术语增加对应主题笔记与开源项目链接。
