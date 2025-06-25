# I Don't Care About Commit Message - Custom

**🌍 Language:** English | [中文](README.zh-CN.md)

---

A customizable AI git commit plugin for VSCode with enhanced configuration options!

This is a fork of the original plugin with additional features like customizable system prompts and lockfile configuration.

![I Don't Care About Commit Message](https://raw.githubusercontent.com/aocuan/vscode-i-dont-care-about-commit-message/main/res/vscode-i-dont-care-about-commit-message.gif "Demonstration of AI Git Commit Plugin")

[🔗 Visit Github Repository](https://github.com/aocuan/vscode-i-dont-care-about-commit-message)

## ✨ Features

- **AI Git Commit**: Simplify your commits with `git add . -> git commit -m "AI Generated Message"`
- **AI Git Push**: Automate the entire process: `git add . -> git commit -m "AI Generated Message" -> git push`
- **AI Git Commit/Push (Minimal)**: Same as above but generates ultra-minimal 1-3 word commit messages
- **Staged Operations**: Same as above, but without using the command `git add .`
- **🆕 Customizable System Prompts**: Configure your own AI prompts for different commit styles
- **🆕 Custom Lockfile Support**: Add your own lockfile types to exclude from analysis

## 🚀 Usage

1. Press `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac)
2. Search for `AI Git Commit` or `AI Git Push`
3. Press `Enter`
4. The plugin will ask for OpenAI API Key if not set, or use GitHub Copilot if enabled
5. Done!

**Pro Tip:** Add keyboard shortcuts to the commands for even faster commits!

## ⚙️ Settings

### OpenAI Configuration
- **OpenAI API Key**: Your OpenAI API key for GPT models
- **OpenAI Base URL**: Custom API endpoint (default: `https://api.openai.com/v1`)
- **Model**: Choose your preferred model (default: `gpt-3.5-turbo`)

Consider these advanced models:
- `gpt-3.5-turbo-16k`: Ideal for large file changes, although it can increase cost
- `gpt-4`: An upgrade but at a higher expense

For more options, visit [OpenAI Models Documentation](https://platform.openai.com/docs/models).

### GitHub Copilot
- **Use Copilot**: Enable to use GitHub Copilot instead of OpenAI API (requires active subscription)
- **Select Copilot Model**: Choose specific Copilot model via command palette

### 🆕 Custom Configuration
- **System Prompt**: Customize the AI prompt for regular commit messages
- **Minimal Prompt**: Customize the AI prompt for minimal commit messages
- **Excluded Lockfiles**: Add/remove lockfile types to exclude from git diff analysis

Default supported lockfiles:
- `package-lock.json`, `yarn.lock` (Node.js)
- `Gemfile.lock` (Ruby)
- `composer.lock` (PHP)
- `pnpm-lock.yaml` (PNPM)
- `go.sum` (Go)
- `cargo.lock` (Rust)
- `poetry.lock` (Python)
- `mix.lock` (Elixir)

### Conventional Commits
- **Use Conventional Commit**: Generate commits in conventional format
- Format: `<type>[optional scope]: <description>`

Examples:
```
feat(auth): add OAuth2 login support
fix(ui): resolve button styling issue
docs: update API documentation
```

> Note: Using conventional commits will be slower and slightly more expensive since it needs to generate more content.

## 🌍 Language Support

The plugin interface supports 14+ languages, making it accessible for developers around the world:

| Language            | Code   | Language            | Code   |
| ------------------- | ------ | ------------------- | ------ |
| English (US)        | en     | Italiano            | it     |
| 简体中文             | zh-cn  | Español             | es     |
| 繁體中文             | zh-tw  | 日本語               | ja     |
| Français            | fr     | 한국어               | ko     |
| Deutsch             | de     | Русский             | ru     |
| Português (Brasil)  | pt-br  | Türkçe              | tr     |
| Polski              | pl     | Čeština             | cs     |
| Magyar              | hu     |                     |        |

## 🛠️ Development

For development, follow these steps:

1. Clone the repository and navigate into it
2. Run `npm install` to install all the necessary dependencies
3. Run `npm run watch` to start the development server
4. Press `F5` to start the plugin in a new VSCode window

For testing, run `npm test`.

## 🙏 Credits

- `I don't care about cookies`: For the funny way of naming
- [Simple Git](https://github.com/steveukx/git-js) @steveukx: It would be much harder without this
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/): For the conventional commit format
  > The `Conventional Commits` format used in this tool is based on the [Conventional Commits specification (v1.0.0)](https://www.conventionalcommits.org/en/v1.0.0/), which is licensed under [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/).
- [aicommits](https://github.com/Nutlope/aicommits) @Nutlope: The CLI AI commit tool I used before I created my own
- [OpenAI API](https://platform.openai.com/docs/api-reference/chat): It makes this AI git extension possible
- [GitHub Copilot](https://github.com/features/copilot): Alternative AI provider for generating commit messages
- [weekly](https://github.com/ruanyf/weekly) @ruanyf: For making this project known and used by more people

## 📄 License

MIT

## 👥 Contributors

- **[@aocuan](https://github.com/aocuan)** - Custom version maintainer
- **[@mefengl](https://github.com/mefengl)** - Original plugin author