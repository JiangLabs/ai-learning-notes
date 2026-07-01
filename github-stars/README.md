# GitHub Stars

## 文件用途

把“收藏过”变成“真正学过”。每篇笔记聚焦一个开源项目，记录核心思路、源码入口、产品启发与学习进度。

## 核心问题

- 这个项目解决什么问题，最重要的设计选择是什么？
- 哪些源码或文档值得优先阅读？
- 它对产品工作和个人实验有什么可迁移的启发？

## 当前文件索引

- [claude-code-from-scratch.md](claude-code-from-scratch.md)：从零复现 Claude Code 核心架构的学习笔记
- [how-claude-code-works.md](how-claude-code-works.md)：从真实源码理解 Claude Code 生产级架构的学习笔记

## ⭐ Learning Order

### ★★★★★ 1. How Claude Code Works

**为什么：** 建立 Coding Agent 架构思维。

### ★★★★★ 2. Claude Code From Scratch

**为什么：** 结合源码理解整体实现。

### ★★★★☆ 3. OpenAI Agents SDK

用于理解 SDK 形式的 Agent 编排与工程边界。项目笔记待补充。

### ★★★★★ 4. Vercel AI SDK

用于连接模型能力、流式交互与前端产品实现。项目笔记待补充。

### ★★★★★ 5. LangGraph

用于理解有状态 Agent 工作流、控制流和恢复机制。项目笔记待补充。

### ★★★★☆ 6. Continue

用于观察开源 Coding Agent 如何进入真实开发工作流。项目笔记待补充。

> 以后每新增一个 GitHub 项目，都要同步维护这里的学习顺序、优先级和推荐理由。

## 建议阅读关系

先通过 How Claude Code Works 建立完整架构地图，再通过 Claude Code From Scratch 跟着精简实现动手验证。前者回答“生产系统为什么这样设计”，后者回答“核心机制怎样跑起来”。

## 知识沉淀原则

GitHub Stars 记录具体项目的实现特点、设计思路和产品启发；通用概念统一沉淀到 [Knowledge](../knowledge/)。

- [Agent Loop](../knowledge/agent/agent-loop.md)
- [Tool / Skills / MCP](../knowledge/agent/tools-skills-mcp.md)
- [Context / Memory](../knowledge/agent/context-memory.md)
- [Prompt、Plan Mode、Multi-Agent 等 Agent 知识](../knowledge/agent/)

项目笔记引用这些知识页，不重复维护通用定义。发现新的通用知识时，先更新 Knowledge，再从项目笔记链接过去。

## 学习 / 记录模板

项目基本信息 → 为什么值得学习 → 推荐阅读顺序 → 核心架构 → 产品启发 → 待学习问题 → 学习进度。

## 后续更新方向

- 增加更多 Agent、AI 产品工程和前端开源项目。
- 为完成阅读的项目补充源码路径、实验记录和结论变化。
- 每新增一个项目，同步更新 Learning Order 和相关 Knowledge 链接。
