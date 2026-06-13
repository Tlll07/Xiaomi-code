# Usage Guide / 使用指南

[English](#english) | [中文](#chinese)

---

<a id="english"></a>
## English

### Basic Workflow

MiMo Code uses a **Plan → Build** workflow:

```
User Request → Plan Mode → Review → Build Mode → Test → Done
```

#### Step 1: Make a Request

Simply describe what you want to do:

```
> Fix the bug in src/utils.js where dates are not parsed correctly
```

#### Step 2: Review the Plan

MiMo Code will analyze your request and create a structured plan. You can:

- **Approve** — Press Enter or type `y` to proceed
- **Modify** — Provide feedback to adjust the plan
- **Cancel** — Type `n` to abort

#### Step 3: Build

Once approved, MiMo Code implements the changes. You'll see:

- Files being modified
- Code changes with explanations
- Running tests

#### Step 4: Verify

MiMo Code automatically runs tests. If they pass, you're done!

### Plan Mode vs Build Mode

| Mode | Purpose | Commands |
|------|---------|----------|
| **Plan Mode** | Analyze and plan changes | Read-only, no modifications |
| **Build Mode** | Implement the planned changes | File edits, git operations |

### Common Commands

```bash
# Start MiMo Code
mimocode

# Start in a specific directory
mimocode /path/to/project

# Resume last session
mimocode --resume

# Run a one-shot task
mimocode "fix the login bug"
```

### Tips for Better Results

1. **Be specific** — "Fix the null pointer in auth.js line 42" is better than "fix the bug"
2. **Provide context** — Mention relevant files, functions, or error messages
3. **Ask questions** — "How would you approach refactoring this module?"
4. **Iterate** — If the first attempt isn't perfect, provide feedback

### Example Sessions

#### Example 1: Bug Fix

```
> The user profile page crashes when the user has no avatar
> The error is in src/components/UserProfile.jsx
> TypeError: Cannot read property 'url' of undefined

MiMo Code: I found the issue. In UserProfile.jsx line 23,
avatar.url is accessed without checking if avatar exists.
I'll add a null check and provide a default avatar.

[Plan created — press Enter to proceed]

[Building...]
- Modified src/components/UserProfile.jsx
- Added null check for avatar
- Added default avatar fallback

[Tests passed!]
```

#### Example 2: Code Generation

```
> Create a React component for a todo list with:
> - Add new items
> - Mark as complete
> - Delete items
> - Persist to localStorage

MiMo Code: I'll create a TodoList component with all requested features.

[Plan created — press Enter to proceed]

[Building...]
- Created src/components/TodoList.jsx
- Created src/components/TodoItem.jsx
- Created src/hooks/useLocalStorage.js
- Added tests

[Tests passed!]
```

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Enter` | Approve plan / Confirm |
| `Ctrl+C` | Cancel current operation |
| `Ctrl+L` | Clear screen |
| `?` | Show help |

---

<a id="chinese"></a>
## 中文

### 基本工作流程

MiMo Code 使用 **规划 → 构建** 工作流：

```
用户请求 → 规划模式 → 审查 → 构建模式 → 测试 → 完成
```

#### 第一步：提出请求

简单描述你想做什么：

```
> 修复 src/utils.js 中日期解析不正确的 bug
```

#### 第二步：审查计划

MiMo Code 会分析你的请求并创建结构化计划。你可以：

- **批准** — 按回车或输入 `y` 继续
- **修改** — 提供反馈来调整计划
- **取消** — 输入 `n` 中止

#### 第三步：构建

批准后，MiMo Code 开始实现更改。你会看到：

- 被修改的文件
- 代码更改和解释
- 运行测试

#### 第四步：验证

MiMo Code 自动运行测试。如果通过，就完成了！

### 规划模式 vs 构建模式

| 模式 | 用途 | 命令 |
|------|------|------|
| **规划模式** | 分析和规划更改 | 只读，不修改文件 |
| **构建模式** | 实现计划的更改 | 文件编辑、git 操作 |

### 常用命令

```bash
# 启动 MiMo Code
mimocode

# 在指定目录启动
mimocode /path/to/project

# 恢复上次会话
mimocode --resume

# 执行一次性任务
mimocode "修复登录 bug"
```

### 获得更好结果的技巧

1. **要具体** — "修复 auth.js 第 42 行的空指针" 比 "修复 bug" 更好
2. **提供上下文** — 提及相关文件、函数或错误信息
3. **提问** — "你会如何重构这个模块？"
4. **迭代** — 如果第一次不完美，提供反馈

### 示例会话

#### 示例 1：Bug 修复

```
> 用户资料页面在用户没有头像时崩溃
> 错误在 src/components/UserProfile.jsx
> TypeError: Cannot read property 'url' of undefined

MiMo Code: 我找到问题了。在 UserProfile.jsx 第 23 行，
avatar.url 在没有检查 avatar 是否存在的情况下被访问。
我会添加空值检查并提供默认头像。

[计划已创建 — 按回车继续]

[构建中...]
- 修改了 src/components/UserProfile.jsx
- 添加了 avatar 空值检查
- 添加了默认头像回退

[测试通过！]
```

#### 示例 2：代码生成

```
> 创建一个 React 待办事项列表组件，包含：
> - 添加新项目
> - 标记完成
> - 删除项目
> - 持久化到 localStorage

MiMo Code: 我会创建一个包含所有请求功能的 TodoList 组件。

[计划已创建 — 按回车继续]

[构建中...]
- 创建了 src/components/TodoList.jsx
- 创建了 src/components/TodoItem.jsx
- 创建了 src/hooks/useLocalStorage.js
- 添加了测试

[测试通过！]
```

### 快捷键

| 按键 | 操作 |
|------|------|
| `Enter` | 批准计划 / 确认 |
| `Ctrl+C` | 取消当前操作 |
| `Ctrl+L` | 清屏 |
| `?` | 显示帮助 |
