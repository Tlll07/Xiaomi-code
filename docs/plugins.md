# Plugin System / 插件系统

[English](#english) | [中文](#chinese)

---

<a id="english"></a>
## English

### What are Plugins?

Plugins extend MiMo Code with custom integrations, tools, and workflows. Unlike skills (which provide knowledge), plugins add new functionality and external service connections.

### Plugins vs Skills

| Aspect | Plugins | Skills |
|--------|---------|--------|
| Purpose | Add new functionality | Provide domain knowledge |
| Complexity | Full applications | Specialized instructions |
| Integration | External services | Internal workflows |
| Distribution | npm packages | Skill marketplace |

### Plugin Structure

```
my-plugin/
├── .codex-plugin/
│   └── plugin.json
├── src/
│   ├── index.js
│   └── commands/
│       └── mycommand.js
├── tests/
│   └── plugin.test.js
├── README.md
└── package.json
```

### plugin.json

```json
{
  "name": "my-plugin",
  "version": "1.0.0",
  "description": "My custom plugin",
  "main": "src/index.js",
  "author": "Your Name",
  "license": "MIT",
  "commands": {
    "hello": {
      "description": "Say hello",
      "handler": "src/commands/hello.js"
    }
  },
  "hooks": {
    "beforeSave": "src/hooks/beforeSave.js"
  }
}
```

### Creating a Plugin

```bash
# Create plugin scaffolding
mimocode plugin create my-plugin

# This creates the directory structure with:
# - plugin.json
# - src/index.js
# - package.json
# - README.md
```

### Developing Plugins

#### Entry Point (src/index.js)

```javascript
module.exports = {
  name: 'my-plugin',
  
  async activate(context) {
    // Plugin initialization
    console.log('My plugin activated!');
    
    // Register commands
    context.registerCommand('hello', async (args) => {
      return `Hello, ${args.name || 'World'}!`;
    });
  },

  async deactivate() {
    // Cleanup
  }
};
```

#### Command Handler (src/commands/hello.js)

```javascript
module.exports = {
  async execute(args, context) {
    const name = args.name || 'World';
    return `Hello, ${name}!`;
  }
};
```

### Installing Plugins

```bash
# Install from npm
mimocode plugin install my-plugin

# Install from local path
mimocode plugin install ./path/to/plugin

# Install from GitHub
mimocode plugin install github:user/repo
```

### Managing Plugins

```bash
# List installed plugins
mimocode plugin list

# Enable/disable a plugin
mimocode plugin enable my-plugin
mimocode plugin disable my-plugin

# Remove a plugin
mimocode plugin remove my-plugin
```

### Plugin API

Plugins have access to MiMo Code's internal API:

```javascript
// File operations
await context.fs.readFile('path/to/file');
await context.fs.writeFile('path/to/file', content);

// Shell commands
const result = await context.shell.exec('ls -la');

// UI notifications
context.notify('Plugin message!', 'info');

// Access to MiMo Code configuration
const config = context.config.get('apiKey');
```

### Publishing Plugins

```bash
# Build your plugin
mimocode plugin build

# Publish to npm
mimocode plugin publish
```

---

<a id="chinese"></a>
## 中文

### 什么是插件？

插件通过自定义集成、工具和工作流扩展 MiMo Code。与技能（提供知识）不同，插件添加新功能和外部服务连接。

### 插件 vs 技能

| 方面 | 插件 | 技能 |
|------|------|------|
| 用途 | 添加新功能 | 提供领域知识 |
| 复杂度 | 完整应用程序 | 专业指令 |
| 集成 | 外部服务 | 内部工作流 |
| 分发 | npm 包 | 技能市场 |

### 插件结构

```
my-plugin/
├── .codex-plugin/
│   └── plugin.json
├── src/
│   ├── index.js
│   └── commands/
│       └── mycommand.js
├── tests/
│   └── plugin.test.js
├── README.md
└── package.json
```

### plugin.json

```json
{
  "name": "my-plugin",
  "version": "1.0.0",
  "description": "我的自定义插件",
  "main": "src/index.js",
  "author": "你的名字",
  "license": "MIT",
  "commands": {
    "hello": {
      "description": "打招呼",
      "handler": "src/commands/hello.js"
    }
  },
  "hooks": {
    "beforeSave": "src/hooks/beforeSave.js"
  }
}
```

### 创建插件

```bash
# 创建插件脚手架
mimocode plugin create my-plugin

# 这会创建目录结构：
# - plugin.json
# - src/index.js
# - package.json
# - README.md
```

### 开发插件

#### 入口文件 (src/index.js)

```javascript
module.exports = {
  name: 'my-plugin',
  
  async activate(context) {
    // 插件初始化
    console.log('我的插件已激活！');
    
    // 注册命令
    context.registerCommand('hello', async (args) => {
      return `你好，${args.name || '世界'}！`;
    });
  },

  async deactivate() {
    // 清理
  }
};
```

#### 命令处理器 (src/commands/hello.js)

```javascript
module.exports = {
  async execute(args, context) {
    const name = args.name || '世界';
    return `你好，${name}！`;
  }
};
```

### 安装插件

```bash
# 从 npm 安装
mimocode plugin install my-plugin

# 从本地路径安装
mimocode plugin install ./path/to/plugin

# 从 GitHub 安装
mimocode plugin install github:user/repo
```

### 管理插件

```bash
# 列出已安装插件
mimocode plugin list

# 启用/禁用插件
mimocode plugin enable my-plugin
mimocode plugin disable my-plugin

# 移除插件
mimocode plugin remove my-plugin
```

### 插件 API

插件可以访问 MiMo Code 的内部 API：

```javascript
// 文件操作
await context.fs.readFile('path/to/file');
await context.fs.writeFile('path/to/file', content);

// Shell 命令
const result = await context.shell.exec('ls -la');

// UI 通知
context.notify('插件消息！', 'info');

// 访问 MiMo Code 配置
const config = context.config.get('apiKey');
```

### 发布插件

```bash
# 构建插件
mimocode plugin build

# 发布到 npm
mimocode plugin publish
```
