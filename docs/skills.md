# Skills System / 技能系统

[English](#english) | [中文](#chinese)

---

<a id="english"></a>
## English

### What are Skills?

Skills are specialized modules that extend MiMo Code's capabilities. They provide domain-specific knowledge, workflows, and tool integrations for specific tasks.

### Built-in Skills

| Skill | Description | Use Case |
|-------|-------------|----------|
| **imagegen** | Generate or edit raster images | Create photos, illustrations, textures, mockups |
| **openai-docs** | Access OpenAI documentation | Learn about OpenAI products, APIs, and models |
| **plugin-creator** | Create Codex plugins | Scaffold new plugin directories with proper structure |
| **skill-creator** | Create custom skills | Build new skills to extend MiMo Code |
| **skill-installer** | Install skills from repos | Add skills from curated list or GitHub repos |

### Installing Skills

```bash
# List available skills
mimocode skills list

# Install a skill
mimocode skills install imagegen

# Install from GitHub
mimocode skills install github:user/repo
```

### Using Skills

Skills are automatically activated when relevant. For example:

- When you ask to generate an image → `imagegen` skill activates
- When you ask about OpenAI APIs → `openai-docs` skill activates
- When you want to create a plugin → `plugin-creator` skill activates

### Creating Custom Skills

Use the skill-creator to build your own:

```bash
# Start skill creation wizard
mimocode skills create
```

#### Skill Structure

```
my-skill/
├── .codex-plugin/
│   └── plugin.json
├── src/
│   └── index.js
├── README.md
└── package.json
```

#### plugin.json

```json
{
  "name": "my-skill",
  "version": "1.0.0",
  "description": "My custom skill",
  "main": "src/index.js",
  "commands": {
    "mycommand": {
      "description": "Does something useful",
      "handler": "src/index.js"
    }
  }
}
```

### Skill Marketplace

Browse and install community skills:

```bash
# Open skill marketplace
mimocode skills browse

# Search for skills
mimocode skills search "translation"
```

---

<a id="chinese"></a>
## 中文

### 什么是技能？

技能是扩展 MiMo Code 能力的专用模块。它们为特定任务提供领域知识、工作流和工具集成。

### 内置技能

| 技能 | 描述 | 使用场景 |
|------|------|----------|
| **imagegen** | 生成或编辑光栅图片 | 创建照片、插图、纹理、模型 |
| **openai-docs** | 访问 OpenAI 文档 | 了解 OpenAI 产品、API 和模型 |
| **plugin-creator** | 创建 Codex 插件 | 用正确结构搭建新插件目录 |
| **skill-creator** | 创建自定义技能 | 构建新技能来扩展 MiMo Code |
| **skill-installer** | 从仓库安装技能 | 从精选列表或 GitHub 仓库添加技能 |

### 安装技能

```bash
# 列出可用技能
mimocode skills list

# 安装技能
mimocode skills install imagegen

# 从 GitHub 安装
mimocode skills install github:user/repo
```

### 使用技能

技能在相关时自动激活。例如：

- 当你要求生成图片时 → `imagegen` 技能激活
- 当你询问 OpenAI API 时 → `openai-docs` 技能激活
- 当你想创建插件时 → `plugin-creator` 技能激活

### 创建自定义技能

使用 skill-creator 构建你自己的技能：

```bash
# 启动技能创建向导
mimocode skills create
```

#### 技能结构

```
my-skill/
├── .codex-plugin/
│   └── plugin.json
├── src/
│   └── index.js
├── README.md
└── package.json
```

#### plugin.json

```json
{
  "name": "my-skill",
  "version": "1.0.0",
  "description": "我的自定义技能",
  "main": "src/index.js",
  "commands": {
    "mycommand": {
      "description": "做一些有用的事情",
      "handler": "src/index.js"
    }
  }
}
```

### 技能市场

浏览和安装社区技能：

```bash
# 打开技能市场
mimocode skills browse

# 搜索技能
mimocode skills search "翻译"
```
