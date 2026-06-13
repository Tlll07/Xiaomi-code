# Troubleshooting / 常见问题

[English](#english) | [中文](#chinese)

---

<a id="english"></a>
## English

### Installation Issues

#### "command not found: mimocode"

**Cause:** MiMo Code is not installed or not in your PATH.

**Solution:**
```bash
# Check if installed
npm list -g mimocode

# Reinstall if needed
npm install -g mimocode

# Add to PATH (Linux/macOS)
export PATH=$PATH:$(npm config get prefix)/bin
```

#### "Permission denied" during install

**Cause:** Insufficient permissions for global npm install.

**Solution:**
```bash
# Use sudo (Linux/macOS)
sudo npm install -g mimocode

# Or fix npm permissions
npm config set prefix ~/.npm-global
export PATH=$PATH:~/.npm-global/bin
```

### API Connection Issues

#### "Invalid API key"

**Cause:** API key is incorrect or expired.

**Solution:**
```bash
# Verify your API key
mimocode config get apiKey

# Update API key
mimocode config set apiKey sk-your-correct-key

# Test connection
mimocode test
```

#### "Connection timeout"

**Cause:** Network issues or firewall blocking.

**Solution:**
```bash
# Check internet connection
ping api.openai.com

# Configure proxy if needed
mimocode config set proxy http://127.0.0.1:7890

# Increase timeout
mimocode config set timeout 60
```

#### "Rate limit exceeded"

**Cause:** Too many API requests.

**Solution:**
- Wait a few minutes and try again
- Upgrade your API plan
- Use a different model with lower rate limits

### Runtime Issues

#### MiMo Code freezes or hangs

**Solution:**
```bash
# Force quit
Ctrl+C

# Clear cache
rm -rf ~/.mimocode/cache

# Restart
mimocode
```

#### "Context length exceeded"

**Cause:** Conversation is too long for the model.

**Solution:**
- Start a new session: `mimocode --new`
- Clear context: type `/clear` in session
- Use a model with larger context window

#### File permission errors

**Cause:** MiMo Code can't read/write files.

**Solution:**
```bash
# Check file permissions
ls -la /path/to/project

# Fix permissions (Linux/macOS)
chmod -R 755 /path/to/project

# Run as admin (Windows)
# Right-click terminal → Run as administrator
```

### Git Issues

#### "Not a git repository"

**Cause:** Project is not initialized as a git repo.

**Solution:**
```bash
# Initialize git
git init
git add .
git commit -m "Initial commit"
```

#### "Cannot push to remote"

**Cause:** Authentication or permission issues.

**Solution:**
```bash
# Check remote URL
git remote -v

# Update remote URL with token
git remote set-url origin https://<token>@github.com/user/repo.git
```

### Performance Issues

#### Slow response times

**Solutions:**
- Use a faster model (e.g., `gpt-3.5-turbo`)
- Reduce context length: `mimocode config set contextLength 4000`
- Close other applications
- Check network speed

#### High memory usage

**Solutions:**
- Restart MiMo Code periodically
- Use `--compact` mode: `mimocode --compact`
- Reduce context length

### Getting Help

```bash
# Show help
mimocode --help

# Show version
mimocode --version

# Run diagnostics
mimocode doctor

# Check logs
mimocode logs
```

### Still Stuck?

1. Check [GitHub Issues](https://github.com/xiaomi/mimocode/issues)
2. Search existing issues for solutions
3. Open a new issue with:
   - MiMo Code version (`mimocode --version`)
   - Operating system
   - Error message
   - Steps to reproduce

---

<a id="chinese"></a>
## 中文

### 安装问题

#### "command not found: mimocode"

**原因：** MiMo Code 未安装或不在 PATH 中。

**解决方案：**
```bash
# 检查是否已安装
npm list -g mimocode

# 如需要重新安装
npm install -g mimocode

# 添加到 PATH（Linux/macOS）
export PATH=$PATH:$(npm config get prefix)/bin
```

#### 安装时 "Permission denied"

**原因：** 全局 npm 安装权限不足。

**解决方案：**
```bash
# 使用 sudo（Linux/macOS）
sudo npm install -g mimocode

# 或修复 npm 权限
npm config set prefix ~/.npm-global
export PATH=$PATH:~/.npm-global/bin
```

### API 连接问题

#### "Invalid API key"

**原因：** API Key 不正确或已过期。

**解决方案：**
```bash
# 验证你的 API Key
mimocode config get apiKey

# 更新 API Key
mimocode config set apiKey sk-your-correct-key

# 测试连接
mimocode test
```

#### "Connection timeout"

**原因：** 网络问题或防火墙阻止。

**解决方案：**
```bash
# 检查网络连接
ping api.openai.com

# 如需要配置代理
mimocode config set proxy http://127.0.0.1:7890

# 增加超时时间
mimocode config set timeout 60
```

#### "Rate limit exceeded"

**原因：** API 请求过多。

**解决方案：**
- 等待几分钟后重试
- 升级你的 API 计划
- 使用速率限制较低的模型

### 运行时问题

#### MiMo Code 冻结或挂起

**解决方案：**
```bash
# 强制退出
Ctrl+C

# 清除缓存
rm -rf ~/.mimocode/cache

# 重启
mimocode
```

#### "Context length exceeded"

**原因：** 对话对模型来说太长。

**解决方案：**
- 开始新会话：`mimocode --new`
- 清除上下文：在会话中输入 `/clear`
- 使用上下文窗口更大的模型

#### 文件权限错误

**原因：** MiMo Code 无法读写文件。

**解决方案：**
```bash
# 检查文件权限
ls -la /path/to/project

# 修复权限（Linux/macOS）
chmod -R 755 /path/to/project

# 以管理员身份运行（Windows）
# 右键点击终端 → 以管理员身份运行
```

### Git 问题

#### "Not a git repository"

**原因：** 项目未初始化为 git 仓库。

**解决方案：**
```bash
# 初始化 git
git init
git add .
git commit -m "Initial commit"
```

#### "Cannot push to remote"

**原因：** 认证或权限问题。

**解决方案：**
```bash
# 检查远程 URL
git remote -v

# 使用 token 更新远程 URL
git remote set-url origin https://<token>@github.com/user/repo.git
```

### 性能问题

#### 响应时间慢

**解决方案：**
- 使用更快的模型（如 `gpt-3.5-turbo`）
- 减少上下文长度：`mimocode config set contextLength 4000`
- 关闭其他应用程序
- 检查网络速度

#### 内存占用高

**解决方案：**
- 定期重启 MiMo Code
- 使用 `--compact` 模式：`mimocode --compact`
- 减少上下文长度

### 获取帮助

```bash
# 显示帮助
mimocode --help

# 显示版本
mimocode --version

# 运行诊断
mimocode doctor

# 查看日志
mimocode logs
```

### 还是卡住了？

1. 查看 [GitHub Issues](https://github.com/xiaomi/mimocode/issues)
2. 搜索现有 issue 寻找解决方案
3. 开新的 issue，包含：
   - MiMo Code 版本（`mimocode --version`）
   - 操作系统
   - 错误信息
   - 复现步骤
