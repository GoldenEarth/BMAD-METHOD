# Contributing to this project
# 为本项目做出贡献

Thank you for considering contributing to this project! This document outlines the process for contributing and some guidelines to follow.

感谢您考虑为本项目做出贡献！本文档概述了贡献流程和一些需要遵循的准则。

🆕 **New to GitHub or pull requests?** Check out our [beginner-friendly Pull Request Guide](docs/how-to-contribute-with-pull-requests.md) first!

🆕 **是 GitHub 或拉取请求的新手？** 请先查看我们的[新手友好型拉取请求指南](docs/how-to-contribute-with-pull-requests-en-cn.md)！

📋 **Before contributing**, please read our [Guiding Principles](docs/GUIDING-PRINCIPLES.md) to understand the BMad Method's core philosophy and architectural decisions.

📋 **在贡献之前**，请阅读我们的[指导原则](docs/GUIDING-PRINCIPLES-en-cn.md)以了解 BMad 方法的核心理念和架构决策。

Also note, we use the discussions feature in GitHub to have a community to discuss potential ideas, uses, additions and enhancements.

另请注意，我们使用 GitHub 中的讨论功能来建立一个社区，讨论潜在的想法、用途、补充和增强功能。

💬 **Discord Community**: Join our [Discord server](https://discord.gg/gk8jAdXWmj) for real-time discussions:

💬 **Discord 社区**：加入我们的 [Discord 服务器](https://discord.gg/gk8jAdXWmj)进行实时讨论：

- **#general-dev** - Technical discussions, feature ideas, and development questions

  **#general-dev** - 技术讨论、功能想法和开发问题

- **#bugs-issues** - Bug reports and issue discussions

  **#bugs-issues** - 错误报告和问题讨论

## Code of Conduct
## 行为准则

By participating in this project, you agree to abide by our Code of Conduct. Please read it before participating.

参与本项目即表示您同意遵守我们的行为准则。请在参与前阅读。

## How to Contribute
## 如何贡献

### Reporting Bugs
### 报告错误

1. **Check existing issues** first to avoid duplicates

   **首先检查现有问题**以避免重复

2. **Use the bug report template** when creating a new issue - it will guide you through providing:

   **创建新问题时使用错误报告模板** - 它将指导您提供：
   - Clear bug description

     清晰的错误描述
   - Steps to reproduce

     重现步骤
   - Expected vs actual behavior

     预期与实际行为
   - Model/IDE/BMad version details

     模型/IDE/BMad 版本详情
   - Screenshots or links if applicable

     截图或链接（如果适用）

3. **Consider discussing in Discord** (#bugs-issues channel) for quick help

   **考虑在 Discord 的 #bugs-issues 频道讨论**以获得快速帮助

4. **Indicate if you're working on a fix** to avoid duplicate efforts

   **表明您是否正在修复**以避免重复劳动

### Suggesting Features
### 建议功能

1. **Discuss first in Discord** (#general-dev channel) - the feature request template asks if you've done this

   **首先在 Discord 的 #general-dev 频道讨论** - 功能请求模板会询问您是否已这样做

2. **Check existing issues and discussions** to avoid duplicates

   **检查现有问题和讨论**以避免重复

3. **Use the feature request template** when creating an issue - it will guide you through:

   **创建问题时使用功能请求模板** - 它将指导您完成：
   - Confirming Discord discussion

     确认 Discord 讨论
   - Describing the problem it solves

     描述其解决的问题
   - Explaining your solution

     解释您的解决方案
   - Listing alternatives considered

     列出考虑过的替代方案

4. **Be specific** about why this feature would benefit the BMad community

   **具体说明**为什么此功能将有益于 BMad 社区

### Pull Request Process
### 拉取请求流程

⚠️ **Before starting work:**

⚠️ **开始工作前：**

1. **For bugs**: Check if an issue exists (create one using the bug template if not)

   **对于错误**：检查是否存在问题（如果不存在，请使用错误模板创建一个）

2. **For features**: Ensure you've discussed in Discord (#general-dev) AND created a feature request issue

   **对于功能**：确保您已在 Discord (#general-dev) 中讨论过并创建了功能请求问题

3. **For large changes**: Always open an issue first to discuss alignment

   **对于大型更改**：始终先创建一个问题以讨论对齐

Please only propose small granular commits! If its large or significant, please discuss in the discussions tab and open up an issue first. I do not want you to waste your time on a potentially very large PR to have it rejected because it is not aligned or deviates from other planned changes. Communicate and lets work together to build and improve this great community project!

请只提出小而精细的提交！如果更改较大或重要，请先在讨论选项卡中讨论并提出问题。我不希望您在一个可能非常大的拉取请求上浪费时间，结果却因为它未对齐或偏离其他计划的更改而被拒绝。沟通让我们共同努力，建设和改进这个伟大的社区项目！

**Important**: All contributions must align with our [Guiding Principles](docs/GUIDING-PRINCIPLES.md). Key points:

**重要提示**：所有贡献必须符合我们的[指导原则](docs/GUIDING-PRINCIPLES-en-cn.md)。关键点：

- Keep dev agents lean - they need context for coding, not documentation

  保持开发代理精简 - 他们需要编码的上下文，而不是文档

- Web/planning agents can be larger with more complex tasks

  Web/规划代理可以更大，处理更复杂的任务

- Everything is natural language (markdown) - no code in core framework

  一切都是自然语言 (markdown) - 核心框架中没有代码

- Use expansion packs for domain-specific features

  使用扩展包实现特定领域的功能

#### Which Branch for Your PR?
#### 您的 PR 应该提交到哪个分支？

**Submit to `next` branch** (most contributions):

**提交到 `next` 分支**（大多数贡献）：

- ✨ New features or agents

  ✨ 新功能或代理

- 🎨 Enhancements to existing features

  🎨 对现有功能的增强

- 📚 Documentation updates

  📚 文档更新

- ♻️ Code refactoring

  ♻️ 代码重构

- ⚡ Performance improvements

  ⚡ 性能改进

- 🧪 New tests

  🧪 新测试

- 🎁 New expansion packs

  🎁 新扩展包

**Submit to `main` branch** (critical only):

**提交到 `main` 分支**（仅限关键性内容）：

- 🚨 Critical bug fixes that break basic functionality

  🚨 破坏基本功能的关键错误修复

- 🔒 Security patches

  🔒 安全补丁

- 📚 Fixing dangerously incorrect documentation

  📚 修复严重不正确的文档

- 🐛 Bugs preventing installation or basic usage

  🐛 妨碍安装或基本使用的错误

**When in doubt, submit to `next`**. We'd rather test changes thoroughly before they hit stable.

**如有疑问，请提交到 `next` 分支**。我们宁愿在更改进入稳定版之前进行彻底测试。

#### PR Size Guidelines
#### PR 规模指南

- **Ideal PR size**: 200-400 lines of code changes

  **理想的 PR 规模**：200-400 行代码更改

- **Maximum PR size**: 800 lines (excluding generated files)

  **最大的 PR 规模**：800 行（不包括生成的文件）

- **One feature/fix per PR**: Each PR should address a single issue or add one feature

  **每个 PR 一个功能/修复**：每个 PR 应解决一个问题或添加一个功能

- **If your change is larger**: Break it into multiple smaller PRs that can be reviewed independently

  **如果您的更改较大**：将其分解为多个可以独立审查的较小 PR

- **Related changes**: Even related changes should be separate PRs if they deliver independent value

  **相关更改**：即使是相关的更改，如果它们能提供独立的价值，也应作为单独的 PR

#### Breaking Down Large PRs
#### 分解大型 PR

If your change exceeds 800 lines, use this checklist to split it:

如果您的更改超过 800 行，请使用此清单进行拆分：

- [ ] Can I separate the refactoring from the feature implementation?

  [ ] 我可以将重构与功能实现分开吗？

- [ ] Can I introduce the new API/interface in one PR and implementation in another?

  [ ] 我可以在一个 PR 中引入新的 API/接口，在另一个 PR 中实现吗？

- [ ] Can I split by file or module?

  [ ] 我可以按文件或模块拆分吗？

- [ ] Can I create a base PR with shared utilities first?

  [ ] 我可以先创建一个包含共享工具的基础 PR 吗？

- [ ] Can I separate test additions from implementation?

  [ ] 我可以将测试添加与实现分开吗？

- [ ] Even if changes are related, can they deliver value independently?

  [ ] 即使更改是相关的，它们能否独立交付价值？

- [ ] Can these changes be merged in any order without breaking things?

  [ ] 这些更改可以按任何顺序合并而不会破坏任何东西吗？

Example breakdown:

示例分解：

1. PR #1: Add utility functions and types (100 lines)

   PR #1：添加实用程序函数和类型（100 行）

2. PR #2: Refactor existing code to use utilities (200 lines)

   PR #2：重构现有代码以使用实用程序（200 行）

3. PR #3: Implement new feature using refactored code (300 lines)

   PR #3：使用重构后的代码实现新功能（300 行）

4. PR #4: Add comprehensive tests (200 lines)

   PR #4：添加全面的测试（200 行）

**Note**: PRs #1 and #4 could be submitted simultaneously since they deliver independent value and don't depend on each other's merge order.

**注意**：PR #1 和 #4 可以同时提交，因为它们提供独立的价值并且不依赖于彼此的合并顺序。

#### Pull Request Steps
#### 拉取请求步骤

1. Fork the repository

   复刻存储库

2. Create a new branch (`git checkout -b feature/your-feature-name`)

   创建一个新分支 (`git checkout -b feature/your-feature-name`)

3. Make your changes

   进行更改

4. Run any tests or linting to ensure quality

   运行任何测试或代码检查以确保质量

5. Commit your changes with clear, descriptive messages following our commit message convention

   遵循我们的提交消息约定，使用清晰、描述性的消息提交您的更改

6. Push to your branch (`git push origin feature/your-feature-name`)

   推送到您的分支 (`git push origin feature/your-feature-name`)

7. Open a Pull Request against the main branch

   针对主分支发起拉取请求

## Issue Templates
## 问题模板

We use GitHub issue templates to ensure all necessary information is provided:

我们使用 GitHub 问题模板来确保提供所有必要的信息：

- **Bug Reports**: Automatically guides you through providing reproduction steps, environment details, and expected behavior

  **错误报告**：自动指导您提供重现步骤、环境详细信息和预期行为

- **Feature Requests**: Requires Discord discussion confirmation and asks for problem/solution descriptions

  **功能请求**：需要确认 Discord 讨论，并要求提供问题/解决方案描述

Using these templates helps maintainers understand and address your contribution faster.

使用这些模板有助于维护人员更快地理解和处理您的贡献。

## Pull Request Description Guidelines
## 拉取请求描述指南

Keep PR descriptions short and to the point following this template:

遵循此模板，保持 PR 描述简短扼要：

### PR Description Template
### PR 描述模板

Keep your PR description concise and focused. Use this template:

保持您的 PR 描述简洁明了。使用此模板：

```markdown
## What
## 内容

[1-2 sentences describing WHAT changed]
[1-2 句话描述更改了什么]

## Why
## 原因

[1-2 sentences explaining WHY this change is needed]
[1-2 句话解释为什么需要此更改]

Fixes #[issue number] (if applicable)
修复 #[问题编号] (如果适用)

## How
## 方式

[2-3 bullets listing HOW you implemented it]
[2-3 点列出您是如何实现的]

-
-
-

## Testing
## 测试

[1-2 sentences on how you tested this]
[1-2 句话说明您是如何测试的]
```

**Maximum PR description length: 200 words** (excluding code examples if needed)

**PR 描述最大长度：200 字**（如果需要，不包括代码示例）

### Good vs Bad PR Descriptions
### 好的与坏的 PR 描述

❌ **Bad Example:**

❌ **不好的例子：**

> This revolutionary PR introduces a paradigm-shifting enhancement to the system's architecture by implementing a state-of-the-art solution that leverages cutting-edge methodologies to optimize performance metrics and deliver unprecedented value to stakeholders through innovative approaches...
> 
> 这个革命性的 PR 通过实施一种利用尖端方法论来优化性能指标并通过创新方法为利益相关者提供前所未有的价值的先进解决方案，为系统架构引入了范式转变的增强功能...

✅ **Good Example:**

✅ **好的例子：**

> **What:** Added validation for agent dependency resolution
> 
> **内容：** 添加了对代理依赖解析的验证
> 
> **Why:** Build was failing silently when agents had circular dependencies
> 
> **原因：** 当代理存在循环依赖时，构建会静默失败
> 
> **How:**
> 
> **方式：**
>
> - Added cycle detection in dependency-resolver.js
> 
>   在 dependency-resolver.js 中添加了循环检测
> - Throws clear error with dependency chain
> 
>   抛出带有依赖链的清晰错误
> 
>   **Testing:** Tested with circular deps between 3 agents
> 
>   **测试：** 使用 3 个代理之间的循环依赖进行了测试

## Commit Message Convention
## 提交消息约定

Use conventional commits format:
使用常规提交格式：

- `feat:` New feature

  `feat:` 新功能

- `fix:` Bug fix

  `fix:` 错误修复

- `docs:` Documentation only

  `docs:` 仅文档

- `refactor:` Code change that neither fixes a bug nor adds a feature

  `refactor:` 既不修复错误也不添加功能的代码更改

- `test:` Adding missing tests

  `test:` 添加缺失的测试

- `chore:` Changes to build process or auxiliary tools

  `chore:` 对构建过程或辅助工具的更改

Keep commit messages under 72 characters.

提交消息保持在 72 个字符以内。

### Atomic Commits
### 原子提交

Each commit should represent one logical change:

每个提交应代表一个逻辑更改：

- **Do:** One bug fix per commit

  **执行：** 每个提交一个错误修复

- **Do:** One feature addition per commit

  **执行：** 每个提交一个功能添加

- **Don't:** Mix refactoring with bug fixes

  **不要：** 将重构与错误修复混合

- **Don't:** Combine unrelated changes

  **不要：** 合并无关的更改

## Code Style
## 代码风格

- Follow the existing code style and conventions

  遵循现有的代码风格和约定

- Write clear comments for complex logic

  为复杂逻辑编写清晰的注释

## License
## 许可证

By contributing to this project, you agree that your contributions will be licensed under the MIT License.

通过为本项目做出贡献，您同意您的贡献将根据 MIT 许可证进行许可。
