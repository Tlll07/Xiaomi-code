# Installation Guide / 安装指南

[English](#english) | [中文](#chinese)

---

<a id="english"></a>
## English

### System Requirements

| OS | Minimum Version |
|----|-----------------|
| Windows | Windows 10 or later |
| macOS | macOS 12 or later |
| Linux | Ubuntu 20.04 or equivalent |

### Prerequisites

- **Node.js** 18.0 or later
- **npm** 9.0+ or **pnpm** 8.0+

### Install Node.js

#### Windows / macOS

Download from [nodejs.org](https://nodejs.org/) — choose the LTS version.

#### Linux (Ubuntu/Debian)

```bash
# Using nvm (recommended)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
nvm install 18
nvm use 18

# Or using apt
sudo apt update
sudo apt install nodejs npm
```

### Install MiMo Code

```bash
# Using npm
npm install -g mimocode

# Using pnpm
pnpm add -g mimocode
```

### Verify Installation

```bash
mimocode --version
# Should output something like: mimocode x.x.x
```

### Configure API Key

MiMo Code needs an API key to connect to AI models.

#### Option 1: Interactive Setup

```bash
mimocode
# Follow the on-screen prompts to configure your API key
```

#### Option 2: Manual Configuration

```bash
# Set API key via command line
mimocode config set apiKey sk-your-api-key-here

# Or set environment variable (Linux/macOS)
export OPENAI_API_KEY=sk-your-api-key-here

# Or set environment variable (Windows PowerShell)
$env:OPENAI_API_KEY="sk-your-api-key-here"
```

#### Option 3: Config File

Create a config file at `~/.mimocode/config.json`:

```json
{
  "apiKey": "sk-your-api-key-here",
  "model": "gpt-4",
  "theme": "dark"
}
```

### First Run

```bash
# Navigate to your project
cd /path/to/your/project

# Start MiMo Code
mimocode
```

You should see the MiMo Code welcome screen and be ready to start coding!

### Troubleshooting

If you encounter issues, see [Troubleshooting Guide](troubleshooting.md).

---

<a id="chinese"></a>
## 中文

### 系统要求

| 操作系统 | 最低版本 |
|----------|----------|
| Windows | Windows 10 或更高版本 |
| macOS | macOS 12 或更高版本 |
| Linux | Ubuntu 20.04 或同等版本 |

### 前置依赖

- **Node.js** 18.0 或更高版本
- **npm** 9.0+ 或 **pnpm** 8.0+

### 安装 Node.js

#### Windows / macOS

从 [nodejs.org](https://nodejs.org/) 下载安装 — 选择 LTS 版本。

#### Linux (Ubuntu/Debian)

```bash
# 使用 nvm（推荐）
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
nvm install 18
nvm use 18

# 或使用 apt
sudo apt update
sudo apt install nodejs npm
```

### 安装 MiMo Code

```bash
# 使用 npm
npm install -g mimocode

# 使用 pnpm
pnpm add -g mimocode
```

### 验证安装

```bash
mimocode --version
# 应该输出类似：mimocode x.x.x
```

### 配置 API Key

MiMo Code 需要 API Key 来连接 AI 模型。

#### 方式 1：交互式设置

```bash
mimocode
# 按照屏幕提示配置 API Key
```

#### 方式 2：手动配置

```bash
# 通过命令行设置 API Key
mimocode config set apiKey sk-your-api-key-here

# 或设置环境变量（Linux/macOS）
export OPENAI_API_KEY=sk-your-api-key-here

# 或设置环境变量（Windows PowerShell）
$env:OPENAI_API_KEY="sk-your-api-key-here"
```

#### 方式 3：配置文件

在 `~/.mimocode/config.json` 创建配置文件：

```json
{
  "apiKey": "sk-your-api-key-here",
  "model": "gpt-4",
  "theme": "dark"
}
```

### 首次运行

```bash
# 进入你的项目目录
cd /path/to/your/project

# 启动 MiMo Code
mimocode
```

你应该能看到 MiMo Code 的欢迎界面，然后就可以开始编程了！

### 故障排除

如果遇到问题，请参阅[常见问题指南](troubleshooting.md)。
