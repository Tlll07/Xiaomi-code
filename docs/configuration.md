# Configuration / 配置说明

[English](#english) | [中文](#chinese)

---

<a id="english"></a>
## English

### Configuration File Location

| OS | Path |
|----|------|
| Windows | `%USERPROFILE%\.mimocode\config.json` |
| macOS/Linux | `~/.mimocode/config.json` |

### Configuration Options

```json
{
  "apiKey": "sk-your-api-key",
  "model": "gpt-4",
  "theme": "dark",
  "language": "en",
  "proxy": "",
  "plugins": [],
  "skills": ["imagegen", "openai-docs"],
  "autoApprove": false,
  "contextLength": 128000
}
```

### Available Settings

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `apiKey` | string | `""` | Your AI provider API key |
| `model` | string | `"gpt-4"` | AI model to use |
| `theme` | string | `"dark"` | UI theme (`dark`, `light`, `auto`) |
| `language` | string | `"en"` | Interface language |
| `proxy` | string | `""` | HTTP proxy URL |
| `plugins` | array | `[]` | Enabled plugins |
| `skills` | array | `[]` | Enabled skills |
| `autoApprove` | boolean | `false` | Auto-approve small changes |
| `contextLength` | number | `128000` | Max context window size |

### Setting Values

#### Via Command Line

```bash
# Set a value
mimocode config set model gpt-4-turbo

# Get a value
mimocode config get model

# List all config
mimocode config list
```

#### Via Config File

Edit `~/.mimocode/config.json` directly:

```bash
# Open in default editor
mimocode config edit

# Or manually
code ~/.mimocode/config.json  # VS Code
vim ~/.mimocode/config.json    # Vim
nano ~/.mimocode/config.json   # Nano
```

### Environment Variables

MiMo Code respects these environment variables:

| Variable | Description |
|----------|-------------|
| `OPENAI_API_KEY` | OpenAI API key |
| `MIMOCODE_MODEL` | Default model |
| `MIMOCODE_THEME` | UI theme |
| `HTTP_PROXY` | HTTP proxy |
| `HTTPS_PROXY` | HTTPS proxy |

### Model Selection

#### OpenAI Models

```bash
mimocode config set model gpt-4           # GPT-4
mimocode config set model gpt-4-turbo     # GPT-4 Turbo
mimocode config set model gpt-3.5-turbo   # GPT-3.5 Turbo
```

#### Other Providers

```bash
# Anthropic Claude
mimocode config set model claude-3-opus
mimocode config set apiKey sk-ant-your-key
mimocode config set baseUrl https://api.anthropic.com

# Google Gemini
mimocode config set model gemini-pro
mimocode config set apiKey your-google-key
mimocode config set baseUrl https://generativelanguage.googleapis.com
```

### Theme Customization

```bash
# Set theme
mimocode config set theme dark
mimocode config set theme light
mimocode config set theme auto  # Follows system preference
```

### Proxy Configuration

```bash
# Set proxy
mimocode config set proxy http://127.0.0.1:7890

# Or use environment variable
export HTTPS_PROXY=http://127.0.0.1:7890
```

### Reset Configuration

```bash
# Reset to defaults
mimocode config reset

# Or delete config file
rm ~/.mimocode/config.json
```

---

<a id="chinese"></a>
## 中文

### 配置文件位置

| 操作系统 | 路径 |
|----------|------|
| Windows | `%USERPROFILE%\.mimocode\config.json` |
| macOS/Linux | `~/.mimocode/config.json` |

### 配置选项

```json
{
  "apiKey": "sk-your-api-key",
  "model": "gpt-4",
  "theme": "dark",
  "language": "zh",
  "proxy": "",
  "plugins": [],
  "skills": ["imagegen", "openai-docs"],
  "autoApprove": false,
  "contextLength": 128000
}
```

### 可用设置

| 设置 | 类型 | 默认值 | 描述 |
|------|------|--------|------|
| `apiKey` | string | `""` | 你的 AI 提供商 API Key |
| `model` | string | `"gpt-4"` | 使用的 AI 模型 |
| `theme` | string | `"dark"` | UI 主题（`dark`、`light`、`auto`） |
| `language` | string | `"en"` | 界面语言 |
| `proxy` | string | `""` | HTTP 代理 URL |
| `plugins` | array | `[]` | 启用的插件 |
| `skills` | array | `[]` | 启用的技能 |
| `autoApprove` | boolean | `false` | 自动批准小更改 |
| `contextLength` | number | `128000` | 最大上下文窗口大小 |

### 设置值

#### 通过命令行

```bash
# 设置值
mimocode config set model gpt-4-turbo

# 获取值
mimocode config get model

# 列出所有配置
mimocode config list
```

#### 通过配置文件

直接编辑 `~/.mimocode/config.json`：

```bash
# 用默认编辑器打开
mimocode config edit

# 或手动编辑
code ~/.mimocode/config.json  # VS Code
vim ~/.mimocode/config.json    # Vim
nano ~/.mimocode/config.json   # Nano
```

### 环境变量

MiMo Code 支持以下环境变量：

| 变量 | 描述 |
|------|------|
| `OPENAI_API_KEY` | OpenAI API Key |
| `MIMOCODE_MODEL` | 默认模型 |
| `MIMOCODE_THEME` | UI 主题 |
| `HTTP_PROXY` | HTTP 代理 |
| `HTTPS_PROXY` | HTTPS 代理 |

### 模型选择

#### OpenAI 模型

```bash
mimocode config set model gpt-4           # GPT-4
mimocode config set model gpt-4-turbo     # GPT-4 Turbo
mimocode config set model gpt-3.5-turbo   # GPT-3.5 Turbo
```

#### 其他提供商

```bash
# Anthropic Claude
mimocode config set model claude-3-opus
mimocode config set apiKey sk-ant-your-key
mimocode config set baseUrl https://api.anthropic.com

# Google Gemini
mimocode config set model gemini-pro
mimocode config set apiKey your-google-key
mimocode config set baseUrl https://generativelanguage.googleapis.com
```

### 主题自定义

```bash
# 设置主题
mimocode config set theme dark
mimocode config set theme light
mimocode config set theme auto  # 跟随系统偏好
```

### 代理配置

```bash
# 设置代理
mimocode config set proxy http://127.0.0.1:7890

# 或使用环境变量
export HTTPS_PROXY=http://127.0.0.1:7890
```

### 重置配置

```bash
# 重置为默认值
mimocode config reset

# 或删除配置文件
rm ~/.mimocode/config.json
```
