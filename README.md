# Claude Code - AI驱动的代码编辑平台

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-ClaudeCode-blue)](https://github.com/DCHEric/ClaudeCode-Source-Code)
[![TypeScript](https://img.shields.io/badge/TypeScript-4.9+-3178C6?logo=typescript)](https://www.typescriptlang.org/)
[![Bun](https://img.shields.io/badge/Bun-1.0+-000000?logo=bun)](https://bun.sh/)
[![Claude AI](https://img.shields.io/badge/Powered%20by-Claude%20AI-orange)](https://www.anthropic.com/)

**强大的 AI 驱动的代码编辑和命令行工具，由 Anthropic 的 Claude AI 模型提供支持**

[快速开始](#-快速开始) • [功能特性](#-核心功能) • [命令参考](#-命令参考) • [架构设计](#-项目架构)

</div>

---

## 📖 项目简介

Claude Code 是一个完整的 AI 驱动代码编辑平台，它将 Claude AI 的强大能力直接集成到您的开发工作流中。通过自然语言与 AI 协作，自动化繁琐的编程任务，提升代码质量和开发效率。

### 🎯 主要特点

- **🤖 AI 代码助手** - 通过自然语言与 Claude 协作编写、重构、优化代码
- **⚡ 自动化工作流** - 自动执行 Git 提交、PR 审查、代码评审等任务
- **🔧 39+ 智能工具** - 文件操作、Bash 执行、Web 搜索、语言服务器等
- **🧩 可扩展架构** - 插件系统、技能系统、MCP 集成支持
- **🎨 现代化 UI** - React + Ink 打造的精美终端界面
- **🔒 安全可控** - 细粒度权限系统，敏感操作需要确认
- **💾 会话持久化** - 保存和恢复对话历史，无缝继续工作
- **🌐 多模式支持** - CLI、Web 应用、浏览器扩展、桌面应用

---

## 🚀 快速开始

### 前置要求

- Node.js 18+ 或 Bun 运行时
- Claude API 密钥（从 [Anthropic Console](https://console.anthropic.com/) 获取）
- Git（用于版本控制功能）

### 安装

```bash
# 克隆仓库
git clone https://github.com/DCHEric/ClaudeCode-Source-Code.git
cd ClaudeCode-Source-Code

# 使用 Bun 安装依赖（推荐）
bun install

# 或使用 npm
npm install
```

### 配置 API 密钥

```bash
# 设置环境变量
export ANTHROPIC_API_KEY=sk-ant-...
```

### 运行

```bash
# 启动交互式 REPL
bun run main.tsx

# 初始化项目
bun run main.tsx init

# 查看所有命令
bun run main.tsx --help
```

---

## ✨ 核心功能

### 1. 智能代码编辑

通过自然语言指令编写和修改代码：

```bash
# 与 AI 交互式编程
"帮我重构这个函数，提高可读性"
"添加类型注解到这个文件"
"优化这段代码的性能"
```

### 2. 自动化 Git 工作流

```bash
# 智能提交
claude commit              # 自动分析变更，生成提交信息

# PR 审查
claude review              # 审查 pull request

# 一键发布
claude commit-push-pr      # 提交、推送并创建 PR
```

### 3. 代码分析和审计

```bash
# 安全审计
claude security-review     # 检测安全漏洞

# 代码审查
claude review-code         # 分析代码质量

# Bug 检测
"帮我找出这段代码的 bug"
```

### 4. 工具集成

39+ 个专业工具开箱即用：

| 工具类型 | 工具名称 | 功能描述 |
|---------|---------|---------|
| **文件操作** | Read, Write, Edit | 文件读写和编辑 |
| **代码搜索** | Glob, Grep | 文件匹配和内容搜索 |
| **命令执行** | Bash | 执行 Shell 命令 |
| **Web 功能** | WebSearch, WebFetch | Web 搜索和页面抓取 |
| **语言服务** | LSP | 代码补全、跳转定义 |
| **MCP 集成** | MCP | 第三方服务集成 |
| **任务管理** | Task, Todo | 任务创建和待办管理 |

### 5. 技能系统

17 个内置技能，支持自定义扩展：

```bash
/batch              # 批处理多个任务
/debug              # 调试模式
/loop               # 循环执行任务
/claudeApi          # 直接调用 Claude API
/skillify           # 创建新技能
```

### 6. MCP（Model Context Protocol）集成

连接第三方服务和工具：

```bash
# 添加 MCP 服务
claude mcp add <service-name>

# 列出已配置的服务
claude mcp list
```

---

## 📦 技术栈

### 核心技术

- **语言**: TypeScript 4.9+
- **运行时**: Bun / Node.js 18+
- **AI 模型**: Anthropic Claude API
- **UI 框架**: React 18 + Ink（终端渲染）
- **构建工具**: Bun

### 主要依赖

```json
{
  "@anthropic-ai/sdk": "Claude API 客户端",
  "@modelcontextprotocol/sdk": "MCP 协议支持",
  "@commander-js/extra-typings": "CLI 框架",
  "react": "UI 组件",
  "zod": "类型验证",
  "ink": "终端 UI 渲染"
}
```

---

## 📁 项目架构

### 核心模块

```
src/
├── main.tsx                 # 主入口（4,683 行）
├── QueryEngine.ts           # AI 查询引擎
├── Tool.ts                  # 工具框架定义
├── commands/                # 103+ 命令实现
├── tools/                   # 39+ 工具实现
├── skills/                  # 技能系统
├── components/              # 144 个 React 组件
├── services/                # 业务逻辑服务
├── state/                   # 状态管理
├── hooks/                   # React Hooks（87 个）
├── utils/                   # 工具函数（332 个文件）
└── types/                   # TypeScript 类型定义
```

### 架构设计

```
┌─────────────────────────────────────────┐
│          用户交互层（CLI/UI）           │
├─────────────────────────────────────────┤
│          命令系统（103+ 命令）          │
├─────────────────────────────────────────┤
│      查询引擎（AI 对话流程管理）        │
├─────────────────────────────────────────┤
│          工具框架（39+ 工具）           │
├─────────────────────────────────────────┤
│      Claude API / MCP / 外部服务        │
└─────────────────────────────────────────┘
```

### 关键组件

| 组件 | 文件 | 说明 |
|------|------|------|
| 查询引擎 | `QueryEngine.ts` | 处理 AI 查询和对话流程 |
| 工具框架 | `Tool.ts` | 定义工具接口和生命周期 |
| 命令系统 | `commands.ts` | 命令注册和路由 |
| 状态管理 | `state/AppState.tsx` | 全局状态管理 |
| 权限系统 | `utils/permissions/` | 工具使用权限控制 |
| MCP 客户端 | `services/mcp/client.ts` | MCP 协议实现 |

---

## 🎯 命令参考

### 项目管理

```bash
claude init                  # 初始化项目 CLAUDE.md
claude config                # 管理配置
claude settings              # 查看设置
```

### Git 工作流

```bash
claude commit                # 创建智能提交
claude commit-push-pr        # 提交、推送并创建 PR
claude review                # 审查 PR
claude security-review       # 安全审计
```

### 上下文管理

```bash
claude context               # 查看/管理上下文
claude memory                # 管理会话记忆
claude clear                 # 清空缓存
```

### 会话管理

```bash
claude session               # 会话操作
claude resume                # 恢复上一个会话
claude cost                  # 查看 API 成本
```

### MCP 集成

```bash
claude mcp add <service>     # 添加 MCP 服务
claude mcp list              # 列出 MCP 服务
claude mcp remove <service>  # 移除 MCP 服务
```

---

## ⚙️ 配置

### 环境变量

```bash
# 必需
ANTHROPIC_API_KEY=sk-ant-...             # Claude API 密钥

# 可选
CLAUDE_CODE_MODEL=claude-3-5-sonnet-20241022  # 指定模型
CLAUDE_CODE_SIMPLE=1                          # 简单模式
CLAUDE_CODE_DISABLE_THINKING=1                # 禁用思考模式
DISABLE_AUTO_COMPACT=1                        # 禁用自动压缩
```

### 配置文件

#### `CLAUDE.md`
项目级指导文件，提供：
- 项目架构说明
- 常见工作流
- 开发规范

#### `.claude/rules/`
自定义规则和指令

#### `.mcp.json`
MCP 服务器配置

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_TOKEN": "your-token"
      }
    }
  }
}
```

---

## 📊 项目统计

| 指标 | 数值 |
|------|------|
| 代码行数 | 512,664 行 |
| TypeScript 文件 | 1,884 个 |
| 命令数量 | 103+ |
| 工具数量 | 39+ |
| React 组件 | 144 个 |
| 服务模块 | 38+ |
| 内置技能 | 17 个 |

---

## 🔑 核心特性详解

### 权限系统

细粒度的工具使用权限控制：

- **自动模式**: 允许的操作自动执行
- **交互模式**: 敏感操作需要确认
- **完全访问**: 信任模式，无限制

### 会话持久化

- 自动保存对话历史
- 无缝恢复工作状态
- 上下文优化和压缩

### 上下文管理

- 自动消息压缩
- Token 使用优化
- 长对话支持

### 插件和扩展

- 动态技能加载
- MCP 协议集成
- 自定义工具开发

---

## 🛠️ 开发指南

### 构建项目

```bash
# 使用 Bun 构建
bun run build

# 运行测试
bun test

# 代码检查
bun run lint
```

### 添加新工具

1. 在 `tools/` 目录创建新工具
2. 实现 `Tool` 接口
3. 在 `tools.ts` 中注册

### 添加新命令

1. 在 `commands/` 目录创建命令文件
2. 使用 Commander.js 定义命令
3. 在 `commands.ts` 中注册

### 创建技能

```bash
# 使用 skillify 工具创建
/skillify <skill-name>
```

---

## 🤝 贡献指南

欢迎贡献代码、报告 bug 或提出新功能建议！

### 贡献流程

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'Add amazing feature'`)
4. 推送到分支 (`git push origin feature/amazing-feature`)
5. 创建 Pull Request

### 代码规范

- 使用 TypeScript 进行类型安全
- 遵循 ESLint 规则
- 编写清晰的注释和文档
- 添加单元测试

---

## 📄 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件

---

## 🔗 相关链接

- [Claude AI](https://www.anthropic.com/)
- [Anthropic API 文档](https://docs.anthropic.com/)
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [Bun 官网](https://bun.sh/)

---

## 📧 联系方式

- 项目主页: [https://github.com/DCHEric/ClaudeCode-Source-Code](https://github.com/DCHEric/ClaudeCode-Source-Code)
- 问题反馈: [GitHub Issues](https://github.com/DCHEric/ClaudeCode-Source-Code/issues)

---

<div align="center">

**⭐ 如果这个项目对你有帮助，请给个 Star！**

Made with ❤️ by [DCHEric](https://github.com/DCHEric)

Powered by [Claude AI](https://www.anthropic.com/)

</div>
