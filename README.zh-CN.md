# 我不在乎提交消息 - 定制版

**🌍 语言:** [English](README.md) | 中文

---

一个可定制的 VSCode AI Git 提交消息插件，支持增强配置选项！

这是原版插件的分支版本，增加了可定制系统提示词和锁文件配置等额外功能。

![我不在乎提交消息](https://raw.githubusercontent.com/aocuan/vscode-i-dont-care-about-commit-message/main/res/vscode-i-dont-care-about-commit-message.gif "AI Git 提交插件演示")

[🔗 访问 Github 仓库](https://github.com/aocuan/vscode-i-dont-care-about-commit-message)

## ✨ 主要功能

- **AI Git 提交**: 简化提交流程 `git add . -> git commit -m "AI生成的消息"`
- **AI Git 推送**: 自动化完整流程：`git add . -> git commit -m "AI生成的消息" -> git push`
- **AI Git 提交/推送（极简）**: 同上但生成超简洁的1-3个词的提交消息
- **暂存操作**: 同上功能，但不使用 `git add .` 命令
- **🆕 可定制系统提示词**: 为不同的提交风格配置您自己的AI提示词
- **🆕 自定义锁文件支持**: 添加您自己的锁文件类型以从分析中排除

## 🚀 使用方法

1. 按 `Ctrl+Shift+P` (Windows/Linux) 或 `Cmd+Shift+P` (Mac)
2. 搜索 `AI Git 提交` 或 `AI Git 推送`
3. 按 `回车`
4. 如未设置，插件会要求输入 OpenAI API 密钥，或使用已启用的 GitHub Copilot
5. 完成！

**专业提示:** 为命令添加键盘快捷键，提交更快速！

## ⚙️ 设置选项

### OpenAI 配置
- **OpenAI 密钥**: 用于 GPT 模型的 OpenAI API 密钥
- **OpenAI 接口地址**: 自定义 API 端点（默认：`https://api.openai.com/v1`）
- **模型选择**: 选择您偏好的模型（默认：`gpt-3.5-turbo`）

推荐的高级模型：
- `gpt-3.5-turbo-16k`: 适合大文件变更，但可能增加成本
- `gpt-4`: 更高质量但费用更高

### GitHub Copilot
- **使用 Copilot**: 启用后使用 GitHub Copilot 而不是 OpenAI API（需要 Copilot 订阅）
- **选择 Copilot 模型**: 通过命令面板选择特定的 Copilot 模型

### 🆕 自定义配置
- **系统提示词**: 自定义常规提交消息的 AI 提示词
- **极简提示词**: 自定义极简提交消息的 AI 提示词
- **排除的锁文件**: 添加/移除要从 git diff 分析中排除的锁文件类型

默认支持的锁文件：
- `package-lock.json`, `yarn.lock` (Node.js)
- `Gemfile.lock` (Ruby)
- `composer.lock` (PHP)
- `pnpm-lock.yaml` (PNPM)
- `go.sum` (Go)
- `cargo.lock` (Rust)
- `poetry.lock` (Python)
- `mix.lock` (Elixir)

### 规范化提交
- **使用规范化提交**: 生成符合约定式提交格式的消息
- 格式：`<类型>[可选范围]: <描述>`

示例：
```
feat(auth): 添加 OAuth2 登录支持
fix(ui): 修复按钮样式问题
docs: 更新 API 文档
```

> 注意：使用规范化提交会稍微慢一些且费用略高，因为需要生成更多内容。

## 🌍 语言支持

插件界面支持 14+ 种语言：

| 语言                | 代码   | 语言                | 代码   |
| ------------------- | ------ | ------------------- | ------ |
| English (US)        | en     | Italiano            | it     |
| 简体中文             | zh-cn  | Español             | es     |
| 繁體中文             | zh-tw  | 日本語               | ja     |
| Français            | fr     | 한국어               | ko     |
| Deutsch             | de     | Русский             | ru     |
| Português (Brasil)  | pt-br  | Türkçe              | tr     |
| Polski              | pl     | Čeština             | cs     |
| Magyar              | hu     |                     |        |

## 🛠️ 开发

1. 克隆仓库并进入目录
2. 运行 `npm install` 安装依赖
3. 运行 `npm run watch` 启动开发服务器
4. 按 `F5` 在新的 VSCode 窗口中启动插件

测试：运行 `npm test`

## 🙏 致谢

- `I don't care about cookies`: 有趣的命名灵感
- [Simple Git](https://github.com/steveukx/git-js) @steveukx: 没有它会很困难
- [Conventional Commits](https://www.conventionalcommits.org/zh-hans/v1.0.0/): 约定式提交格式
- [aicommits](https://github.com/Nutlope/aicommits) @Nutlope: 我之前使用的 CLI AI 提交工具
- [OpenAI API](https://platform.openai.com/docs/api-reference/chat): 让这个插件成为可能
- [GitHub Copilot](https://github.com/features/copilot): 替代的 AI 提供商
- [weekly](https://github.com/ruanyf/weekly) @ruanyf: 让更多人知道并使用这个项目

## 📄 许可证

MIT

## 👥 贡献者

- **[@aocuan](https://github.com/aocuan)** - 定制版维护者
- **[@mefengl](https://github.com/mefengl)** - 原版插件作者