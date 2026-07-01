# AI Product Engineering OS

> 一个长期维护的 AI 产品工程学习与实践系统。

## 仓库定位

这里沉淀我的 AI 产品工程学习、开源项目研究、Agent / MCP / Skills 知识体系、前端工程实践、工作产品思考、个人实验和每周复盘。它不是资料收藏夹，而是一套把输入、理解、实践和复盘连接起来的个人工作系统。

## 为什么维护这个仓库

AI 产品正在重新连接产品、设计与工程。对产品经理和设计背景的学习者来说，真正的难点不是知道更多名词，而是形成技术理解、产品判断和动手能力之间的闭环。这个仓库用于减少重复学习，让每次阅读、实验和工作思考都能留下可继续使用的结果。

## 我的长期目标

- 能独立理解并设计 Agent、Tool、Skill、MCP、Context 与 Memory 系统。
- 能用 TypeScript、React、Next.js 和 AI SDK 做出可验证的产品原型。
- 能从源码和优秀开源项目中提炼架构选择，而不是只停留在产品体验。
- 能把 MobileFlow、Insight、CodeFuse ONE 等工作问题转化为可验证的 AI 产品方案。
- 逐步形成“产品判断 + 设计表达 + 工程实现”的 AI Product Engineer 能力组合。

## Current Learning Path

这是整个仓库的默认学习路线。当前阶段先建立 AI Agent 与 Coding Agent 的基础理解，工作沉淀和个人实验随后逐步展开。

### 第一阶段（当前）

1. **[AI Product Engineer Roadmap](roadmap/ai-product-engineer-roadmap.md)**
   - 目的：建立未来 6～12 个月的成长路线，明确当前能力、目标能力和学习重点。
2. **[How Claude Code Works](github-stars/how-claude-code-works.md)**
   - 目的：理解 Coding Agent 为什么这样设计，建立整体架构思维。
3. **[Claude Code From Scratch](github-stars/claude-code-from-scratch.md)**
   - 目的：结合实现理解 Agent Loop、Tool、Memory、Context、MCP 等核心能力。

### 第二阶段（后续）

1. OpenAI Agents SDK
2. [Vercel AI SDK](knowledge/frontend/vercel-ai-sdk.md)
3. LangGraph
4. Continue

### 第三阶段（未来）

1. 学习更多优秀 GitHub 项目。
2. 完成自己的 AI Demo。
3. 开展自己的产品实验。

## 建议优先补充

1. [AI Product Engineer Roadmap](roadmap/ai-product-engineer-roadmap.md)
2. [How Claude Code Works](github-stars/how-claude-code-works.md)
3. [Claude Code From Scratch](github-stars/claude-code-from-scratch.md)

当前阶段先补齐 AI Agent 基础知识。Work 模块不作为默认学习起点，可以随着真实工作问题逐步完善。

## Learning Principles

1. **先理解产品，不要先研究代码。**
   - 先弄清产品解决谁的什么问题，再进入技术实现。
2. **先理解架构，不要逐行阅读源码。**
   - 先建立模块、数据流和关键取舍的整体地图，再选择重点源码。
3. **代码是理解设计思想的工具，不是学习目标。**
   - 阅读代码是为了验证架构判断和产品机制，不以读完代码量衡量进度。
4. **GitHub Stars 用来学习案例，Knowledge 用来沉淀知识。**
   - 不在多个项目笔记中重复维护同一套通用概念。
5. **每学习一个 GitHub 项目，都要把通用知识沉淀到 Knowledge。**
   - 项目笔记只保留该项目的实现特点、设计思路和启发，并引用对应 Knowledge 页面。

## 核心模块

| 模块 | 用途 |
| --- | --- |
| [github-stars/](github-stars/) | 深读优秀开源项目，记录架构、源码入口与产品启发 |
| [knowledge/](knowledge/) | 建立 AI、Agent、MCP、Skills、Coding Agent 和前端知识体系 |
| [work/](work/) | 沉淀 MobileFlow、Insight、CodeFuse ONE 等真实工作思考 |
| [projects/](projects/) | 管理个人 Demo、产品想法和实验记录 |
| [roadmap/](roadmap/) | 维护长期能力路线、阶段重点与月度计划 |
| [weekly-notes/](weekly-notes/) | 每周复盘输入、理解、工作启发和下一步行动 |

## GitHub 项目索引

- [Claude Code From Scratch](github-stars/claude-code-from-scratch.md)：用精简实现从零理解 Coding Agent 的核心架构
- [How Claude Code Works](github-stars/how-claude-code-works.md)：从真实源码理解 Claude Code 的生产级架构与设计取舍

## 如何记录一个 GitHub 项目

1. 在 github-stars 新建项目名对应的 Markdown 文件。
2. 先写项目基本信息、学习目标和推荐阅读顺序。
3. 用自己的话拆解关键架构，不整段搬运项目 README。
4. 写清楚它对产品设计、当前工作和个人项目的启发。
5. 留下待学习问题、进度和下一步，让笔记可以持续生长。

可以从上面的项目笔记开始：先用 How Claude Code Works 建立生产级架构视角，再用 Claude Code From Scratch 动手验证核心机制。

## 如何做每周复盘

每周用一篇短笔记回答六个问题：学了什么、看了哪些项目、理解了哪些概念、对工作有什么启发、下周做什么、还想问什么。重点不是统计时间，而是确认这一周有哪些认知变化、产出和下一步行动。

模板见 [2026 Week 01](weekly-notes/2026-week-01.md)。

## 如何使用 Codex 维护这个仓库

- 新增内容前，让 Codex 先检查现有目录和索引，避免重复文件。
- 提供项目链接时，让 Codex 先核对原始资料，再按现有笔记风格整理。
- 重构目录时要求优先迁移和合并，并检查所有本地链接。
- 每次修改后让 Codex 输出变更摘要、目录树和未解决问题。
- commit 和 push 保持人工确认；笔记内容也要由我补充真实判断与实践结果。

## 维护原则

- 先记录真实问题，再补概念；先做小实验，再写大结论。
- 允许旧观点被修订，但保留认知变化的原因。
- 每篇笔记都尽量连接到工作、项目或下一步行动。
- 内容以未来的自己能快速继续为准，保持简洁、可检索、可更新。
