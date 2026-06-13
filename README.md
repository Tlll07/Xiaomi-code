# MiMo Code

[English](#english) | [中文](#chinese)

---

<a id="english"></a>
## English

**MiMo Code** is an AI-powered CLI coding assistant built by the Xiaomi MiMo Team. It helps developers with software engineering tasks — from writing code and fixing bugs to refactoring and understanding codebases.

### Why MiMo Code?

- **Interactive CLI** — Works directly in your terminal, no GUI required
- **Plan + Build Workflow** — Think before you code with structured planning
- **Skills System** — Extend capabilities with specialized skills (image generation, docs lookup, plugin creation, etc.)
- **Plugin System** — Add custom integrations and tools
- **Memory System** — Remembers your project context across sessions
- **Multi-model Support** — Use OpenAI, Xiaomi MiMo, or other compatible models

### Quick Install

```bash
# Install globally
npm install -g mimocode

# Or with pnpm
pnpm add -g mimocode

# Verify installation
mimocode --version
```

### Configure API Key

```bash
# Set your OpenAI API key
mimocode config set apiKey sk-your-api-key-here

# Or use environment variable
export OPENAI_API_KEY=sk-your-api-key-here
```

### First Run

```bash
# Start MiMo Code in your project directory
cd your-project
mimocode
```

### How It Works

1. **Ask** — Describe what you want to do in natural language
2. **Plan** — MiMo Code analyzes your request and creates a plan
3. **Build** — Approve the plan and MiMo Code implements it
4. **Test** — Run tests to verify the changes

### Core Features

| Feature | Description |
|---------|-------------|
| Code Generation | Write new code from natural language descriptions |
| Bug Fixing | Identify and fix bugs with explanations |
| Refactoring | Improve code structure and readability |
| Code Review | Analyze code for issues and suggestions |
| Testing | Generate and run tests |
| Git Integration | Create commits and pull requests |

### Learn More

- [Installation Guide](docs/installation.md) — Detailed setup instructions
- [Usage Guide](docs/usage.md) — How to use MiMo Code effectively
- [Skills System](docs/skills.md) — Extend MiMo Code with skills
- [Plugin System](docs/plugins.md) — Build custom plugins
- [Configuration](docs/configuration.md) — All settings and options
- [Troubleshooting](docs/troubleshooting.md) — Common issues and solutions

### License

MIT License

---

<a id="chinese"></a>
## 中文

**MiMo Code** 是由小米 MiMo 团队开发的 AI 驱动的命令行编程助手。它帮助开发者完成各种软件工程任务——从编写代码、修复 Bug 到重构代码和理解代码库。

### 为什么选择 MiMo Code？

- **交互式命令行** — 直接在终端中工作，无需图形界面
- **规划 + 构建工作流** — 先思考后编码，结构化规划
- **技能系统** — 通过专业技能扩展能力（图片生成、文档查询、插件创建等）
- **插件系统** — 添加自定义集成和工具
- **记忆系统** — 跨会话记住你的项目上下文
- **多模型支持** — 使用 OpenAI、小米 MiMo 或其他兼容模型

### 快速安装

```bash
# 全局安装
npm install -g mimocode

# 或使用 pnpm
pnpm add -g mimocode

# 验证安装
mimocode --version
```

### 配置 API Key

```bash
# 设置你的 OpenAI API Key
mimocode config set apiKey sk-your-api-key-here

# 或使用环境变量
export OPENAI_API_KEY=sk-your-api-key-here
```

### 首次运行

```bash
# 在你的项目目录中启动 MiMo Code
cd your-project
mimocode
```

### 工作流程

1. **提问** — 用自然语言描述你想做什么
2. **规划** — MiMo Code 分析你的请求并创建计划
3. **构建** — 批准计划后 MiMo Code 开始实现
4. **测试** — 运行测试验证更改

### 核心功能

| 功能 | 描述 |
|------|------|
| 代码生成 | 从自然语言描述生成新代码 |
| Bug 修复 | 识别并修复 Bug，附带解释 |
| 代码重构 | 改善代码结构和可读性 |
| 代码审查 | 分析代码问题并提供建议 |
| 测试生成 | 生成并运行测试 |
| Git 集成 | 创建提交和拉取请求 |

### 了解更多

- [安装指南](docs/installation.md) — 详细的安装说明
- [使用指南](docs/usage.md) — 如何高效使用 MiMo Code
- [技能系统](docs/skills.md) — 用技能扩展 MiMo Code
- [插件系统](docs/plugins.md) — 构建自定义插件
- [配置说明](docs/configuration.md) — 所有设置和选项
- [常见问题](docs/troubleshooting.md) — 常见问题和解决方案

### 许可证

MIT 许可证
