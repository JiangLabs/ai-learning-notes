# Claude Code From Scratch 学习笔记

## 项目基本信息

- 项目名：Claude Code From Scratch
- 项目地址：[Windy3f3f3f3f/claude-code-from-scratch](https://github.com/Windy3f3f3f3f/claude-code-from-scratch)
- 一句话介绍：用约 4300 行 TypeScript / 3800 行 Python，从零复现 Claude Code 核心架构，帮助理解 Coding Agent 的工作原理。
- 我的学习目标：从一个足够小、又足够完整的实现出发，建立对 Coding Agent 运行链路的整体认识。

## 知识沉淀说明

本文只保留 Claude Code From Scratch 的实现特点、设计思路和产品启发。通用概念统一维护在 Knowledge：

- [Agent Loop](../knowledge/agent/agent-loop.md)
- [Tool / Skills / MCP](../knowledge/agent/tools-skills-mcp.md)
- [Context / Memory](../knowledge/agent/context-memory.md)
- [Plan Mode](../knowledge/agent/plan-mode.md)
- [Multi-Agent](../knowledge/agent/multi-agent.md)
- [Prompt 等 Agent 通用知识](../knowledge/agent/)

后续更新这些主题时，优先更新 Knowledge；本文只补充项目中的具体实现和差异。

## 为什么值得学习

Claude Code 这类产品看起来像“会调用终端的聊天机器人”，真正的复杂度却藏在循环控制、工具执行、上下文管理、权限、安全与交互反馈之间。这个项目把黑盒拆成可以逐段阅读的代码，便于把产品体验和底层机制一一对应起来。

## 我应该重点看的章节

项目当前教程分为两个阶段。建议先顺序完成 Phase 1，再按产品关注点选择 Phase 2：

### Phase 1：先做出一个可用的 Coding Agent

1. Agent Loop：调用 LLM、执行工具并持续循环。
2. 工具系统：13 个工具、mtime 防护与延迟加载。
3. System Prompt：提示词工程与 @include 语法。
4. CLI 与会话：REPL、Ctrl+C 和会话持久化。
5. 流式输出：双后端、流式工具执行与并行执行。
6. 权限与安全：权限模式、声明式规则与危险检测。
7. 上下文管理：4 层压缩与大结果持久化。

### Phase 2：补齐进阶能力

8. 记忆系统：4 类记忆、语义召回与异步预取。
9. 技能系统：技能发现，以及 inline / fork 两种模式。
10. Plan Mode：只读规划与审批工作流。
11. 多 Agent：Sub-Agent 的 fork-return 架构。
12. MCP 集成：通过 stdio 上的 JSON-RPC 连接外部工具。
13. 架构对比：对照完整 Claude Code 并寻找扩展方向。
14. 功能测试：用 19 项手动测试覆盖主要能力。

我的优先顺序：先精读 1、2、6、7，建立 Agent 主链路；再读 8–12，理解产品能力如何模块化；最后用 13、14 做整体复盘和动手验证。

> 阅读时补充：对应源码路径、关键类或函数、一次完整调用链。

## Agent Loop：项目实现特点

通用机制见 [Agent Loop](../knowledge/agent/agent-loop.md)。本项目把主循环压缩到可阅读的实现中，清楚展示“调用 LLM → 解析响应 → 执行工具 → 回注结果 → 继续”的代码路径。

阅读重点是循环由谁控制、停止条件怎样判断、工具失败如何恢复，以及终端 UI 怎样反馈执行状态。

## Tool / Skill / MCP：项目实现特点

通用概念见 [Tool / Skills / MCP](../knowledge/agent/tools-skills-mcp.md)。本项目的特点是：

- 用统一接口组织 13 个工具，并加入 mtime 防护、并行执行与延迟加载。
- Skills 支持发现机制和 inline / fork 两种执行方式。
- MCP 通过 stdio 上的 JSON-RPC 接入外部工具。

重点观察三类能力怎样进入同一个 Agent Loop，以及它们如何共享权限、结果回传和错误处理。

## Context / Memory：项目实现特点

通用概念见 [Context / Memory](../knowledge/agent/context-memory.md)。本项目用 4 层压缩和大结果持久化控制上下文，并用 4 类记忆、语义召回和异步预取处理长期信息。

阅读重点是各层机制的触发时机、压缩后的信息损失，以及记忆召回怎样避免无关内容挤占上下文。

## Plan Mode 和 Multi-Agent 的产品启发

Plan Mode 把高风险任务拆成“理解—计划—确认—执行”，让用户在改动发生前校正方向。它不只是让模型多想一步，也建立控制感、可预期性和共同决策。

Multi-Agent 适合可拆分、能并行、需要不同上下文的任务。产品不能只展示“有多个 Agent”，还应说明如何分工、共享证据、处理冲突，以及最终由谁负责答案。

## 对 MobileFlow 的启发

- 把移动端操作建模为目标、步骤、当前状态和完成条件。
- 在支付、发布、删除等高风险动作前提供可编辑计划。
- 显示系统观察到的页面状态与下一步动作，减少黑盒感。
- 为失败步骤设计局部恢复路径，不从头重跑整条 Flow。
- 可探索让子 Agent 分别负责页面理解、规划和验证，但用户只看到清晰主线。

## 对 Insight Skills 的启发

- 把洞察方法封装成可复用 Skill，不只是一段提示词。
- 明确输入、步骤、工具、输出格式和质量检查。
- 将资料检索、证据归纳、反例检查拆开，降低上下文负担。
- 让用户区分证据支持的结论与仍待验证的推断。
- 用真实执行记录评估 Skill 的稳定性并持续迭代。

## 我的待学习问题

- [ ] 一次 Agent Loop 的完整代码调用链是什么？
- [ ] 工具参数如何定义、校验并安全执行？
- [ ] 上下文压缩何时触发，会损失哪些信息？
- [ ] Plan Mode 与普通模式在提示和权限上有何不同？
- [ ] Sub-agent 如何继承目标，又如何隔离无关上下文？
- [ ] Skill 的发现与加载机制是什么？
- [ ] MCP 连接异常时，Agent 如何降级或恢复？
- [ ] TypeScript 与 Python 版本的设计差异有哪些？

## 学习进度

- 当前状态：未开始
- 开始日期：待填写
- 最近更新：待填写
- 已完成章节：待填写
- 下一步：先跑通项目，再画出最小 Agent Loop 的调用链

| 日期 | 阅读内容 / 实验 | 新理解 | 未解决问题 |
| --- | --- | --- | --- |
| 待填写 | 待填写 | 待填写 | 待填写 |

## 后续更新方向

- 跑通 TypeScript 或 Python 版本，补充真实调用链和调试记录。
- 将每章和 How Claude Code Works 的生产级设计建立对应关系。
