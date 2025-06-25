# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Build and Development
- `npm run compile` - Build the extension for production
- `npm run watch` - Start development mode with file watching and source maps
- `npm run vscode:prepublish` - Pre-publish build step

### Testing and Quality
- `npm test` - Run tests using Vitest
- `npm run lint` - Run ESLint for code linting
- `npm run lint:fix` - Auto-fix ESLint issues

### Publishing
- `npm run bump` - Bump version using bumpp
- `npm run publish` - Publish extension to VS Code marketplace
- `npm run release` - Bump version and publish

## Architecture Overview

This is a VSCode extension that provides AI-powered git commit message generation. The extension supports both OpenAI API and GitHub Copilot for generating commit messages.

### Core Components

**src/extension.ts** - Main extension entry point containing:
- Command registration for all git operations (commit, push, staged operations)
- VSCode extension lifecycle management (activate/deactivate)
- Integration with both OpenAI API and GitHub Copilot
- Configuration management for user settings

**src/pure.ts** - Pure utility functions for:
- Git diff processing and analysis
- Conventional commit message formatting
- Lockfile detection and handling
- Chat completion response processing

**src/i18n.ts** - Internationalization system with lazy-loaded locale files from the `locales/` directory

### Key Features

1. **Multiple AI Providers**: Supports both OpenAI API and GitHub Copilot for commit message generation
2. **Conventional Commits**: Optional conventional commit format support
3. **Staged vs All Files**: Separate commands for staged files vs `git add .` operations
4. **Minimal Mode**: Ultra-short 1-3 word commit messages
5. **Internationalization**: 14+ language support with JSON locale files

### Command Structure

The extension registers these VSCode commands:
- `gitCommitAI` / `gitPushAI` - Standard AI commit/push (adds all files)
- `gitCommitStagedAI` / `gitPushStagedAI` - AI commit/push for staged files only
- `gitCommitMinimal` / `gitPushMinimal` - Minimal commit messages
- `gitCommitStagedMinimal` / `gitPushStagedMinimal` - Minimal staged operations
- `gitCommitX` - Quick commit with message "x"
- `selectCopilotModel` - Configure Copilot model selection

### Configuration

Settings are stored under `iDontCareAboutCommitMessage` namespace:
- `openaiApiKey` / `openaiBaseURL` / `model` - OpenAI configuration
- `useCopilot` / `selectedCopilotModel` - Copilot configuration  
- `useConventionalCommit` - Enable conventional commit format

### Testing

Uses Vitest for testing with tests in `test/extension.test.ts`. Tests focus on pure functions in `src/pure.ts` including commit message formatting, git diff processing, and utility functions.

### Dependencies

- **simple-git** - Git operations interface
- **openai** - OpenAI API client
- VSCode Language Model API for Copilot integration
- Standard VSCode extension APIs for UI and configuration