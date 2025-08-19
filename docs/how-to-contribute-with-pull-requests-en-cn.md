# How to Contribute with Pull Requests
# 如何通过拉取请求（Pull Request）进行贡献

**New to GitHub and pull requests?** This guide will walk you through the basics step by step.
**刚接触 GitHub 和拉取请求？** 本指南将带您一步步了解基础知识。

## What is a Pull Request?
## 什么是拉取请求？

A pull request (PR) is how you propose changes to a project on GitHub. Think of it as saying "Here are some changes I'd like to make - please review and consider adding them to the main project."

拉取请求（PR）是您在 GitHub 上提议对项目进行更改的方式。可以把它想象成在说：“这里有一些我想做的更改——请审查并考虑将它们添加到主项目中。”

## Before You Start
## 开始之前

⚠️ **Important**: Please keep your contributions small and focused! We prefer many small, clear changes rather than one massive change.

⚠️ **重要提示**：请保持您的贡献小而专注！我们更喜欢许多小的、清晰的更改，而不是一个巨大的更改。

**Required before submitting PRs:**

**提交 PR 前的要求：**

- **For bug fixes**: Create an issue using the [bug report template](https://github.com/bmadcode/bmad-method/issues/new?template=bug_report.md)

  **对于错误修复**：使用[错误报告模板](https://github.com/bmadcode/bmad-method/issues/new?template=bug_report.md)创建一个问题
- **For new features**:

  **对于新功能**：
  1. Discuss in Discord [#general-dev channel](https://discord.gg/gk8jAdXWmj)
   
     在 Discord 的 [#general-dev 频道](https://discord.gg/gk8jAdXWmj)进行讨论
  2. Create an issue using the [feature request template](https://github.com/bmadcode/bmad-method/issues/new?template=feature_request.md)
   
     使用[功能请求模板](https://github.com/bmadcode/bmad-method/issues/new?template=feature_request.md)创建一个问题
- **For large changes**: Always open an issue first to discuss alignment

  **对于大的更改**：始终先创建一个问题以讨论对齐

## Step-by-Step Guide
## 分步指南

### 1. Fork the Repository
### 1. 复刻（Fork）仓库

1. Go to the [BMad-Method repository](https://github.com/bmadcode/bmad-method)
   
   转到 [BMad-Method 仓库](https://github.com/bmadcode/bmad-method)
2. Click the "Fork" button in the top-right corner
   
   点击右上角的“Fork”按钮
3. This creates your own copy of the project
   
   这会创建您自己的项目副本

### 2. Clone Your Fork
### 2. 克隆您的复刻仓库

```bash
# Replace YOUR-USERNAME with your actual GitHub username
# 将 YOUR-USERNAME 替换为您的实际 GitHub 用户名
git clone https://github.com/YOUR-USERNAME/bmad-method.git
cd bmad-method
```

### 3. Create a New Branch
### 3. 创建一个新分支

**Never work directly on the `main` branch!** Always create a new branch for your changes:

**永远不要直接在 `main` 分支上工作！** 始终为您的更改创建一个新分支：

```bash
# Create and switch to a new branch
# 创建并切换到一个新分支
git checkout -b fix/typo-in-readme
# or
# 或
git checkout -b feature/add-new-agent
```

**Branch naming tips:**

**分支命名技巧：**

- `fix/description` - for bug fixes

  `fix/描述` - 用于错误修复
- `feature/description` - for new features

  `feature/描述` - 用于新功能
- `docs/description` - for documentation changes

  `docs/描述` - 用于文档更改

### 4. Make Your Changes
### 4. 进行更改

- Edit the files you want to change

  编辑您想更改的文件
- Keep changes small and focused on one thing

  保持更改小而专注
- Test your changes if possible

  如果可能，测试您的更改

### 5. Commit Your Changes
### 5. 提交您的更改

```bash
# Add your changes
# 添加您的更改
git add .

# Commit with a clear message
# 使用清晰的消息进行提交
git commit -m "Fix typo in README.md"
```

**Good commit messages:**

**好的提交消息：**

- "Fix typo in installation instructions"

  “修复安装说明中的拼写错误”
- "Add example for new agent usage"

  “为新代理用法添加示例”
- "Update broken link in docs"

  “更新文档中的损坏链接”

**Bad commit messages:**

**不好的提交消息：**

- "stuff"

  “东西”
- "changes"

  “更改”
- "update"

  “更新”

### 6. Push to Your Fork
### 6. 推送到您的复刻仓库

```bash
# Push your branch to your fork
# 将您的分支推送到您的复刻仓库
git push origin fix/typo-in-readme
```

### 7. Create the Pull Request
### 7. 创建拉取请求

1. Go to your fork on GitHub
   
   转到您在 GitHub 上的复刻仓库
2. You'll see a green "Compare & pull request" button - click it
   
   您会看到一个绿色的“Compare & pull request”按钮 - 点击它
3. Select the correct target branch:
   
   选择正确的目标分支：
   - **`next` branch** for most contributions (features, docs, enhancements)

     **`next` 分支**用于大多数贡献（功能、文档、增强）
   - **`main` branch** only for critical fixes

     **`main` 分支**仅用于关键修复
4. Fill out the PR description using the template in CONTRIBUTING.md:
   
   使用 CONTRIBUTING.md 中的模板填写 PR 描述：
   - **What**: 1-2 sentences describing what changed

     **什么**：用 1-2 句话描述更改了什么
   - **Why**: 1-2 sentences explaining why

     **为什么**：用 1-2 句话解释原因
   - **How**: 2-3 bullets on implementation

     **如何**：用 2-3 个要点说明实现方式
   - **Testing**: How you tested

     **测试**：您是如何测试的
5. Reference the related issue number (e.g., "Fixes #123")
   
   引用相关的问题编号（例如，“Fixes #123”）

### 8. Wait for Review
### 8. 等待审查

- A maintainer will review your PR

  维护人员将审查您的 PR
- They might ask for changes

  他们可能会要求更改
- Be patient and responsive to feedback

  耐心并积极响应反馈

## What Makes a Good Pull Request?
## 什么样的拉取请求是好的？

✅ **Good PRs:**

✅ **好的 PR：**

- Change one thing at a time

  一次只更改一件事
- Have clear, descriptive titles

  有清晰、描述性的标题
- Explain what and why in the description

  在描述中解释了什么和为什么
- Include only the files that need to change

  只包含需要更改的文件

❌ **Avoid:**

❌ **避免：**

- Changing formatting of entire files

  更改整个文件的格式
- Multiple unrelated changes in one PR

  在一个 PR 中进行多个不相关的更改
- Copying your entire project/repo into the PR

  将您的整个项目/仓库复制到 PR 中
- Changes without explanation

  没有解释的更改

## Common Mistakes to Avoid
## 要避免的常见错误

1. **Don't reformat entire files** - only change what's necessary
   
   **不要重新格式化整个文件** - 只更改必要的内容
2. **Don't include unrelated changes** - stick to one fix/feature per PR
   
   **不要包含不相关的更改** - 每个 PR 只处理一个修复/功能
3. **Don't paste code in issues** - create a proper PR instead
   
   **不要在问题中粘贴代码** - 而是创建一个合适的 PR
4. **Don't submit your whole project** - contribute specific improvements
   
   **不要提交您的整个项目** - 贡献具体的改进

## Need Help?
## 需要帮助？

- 💬 Join our [Discord Community](https://discord.gg/gk8jAdXWmj) for real-time help:

  💬 加入我们的 [Discord 社区](https://discord.gg/gk8jAdXWmj)以获得实时帮助：
  - **#general-dev** - Technical questions and feature discussions

    **#general-dev** - 技术问题和功能讨论
  - **#bugs-issues** - Get help with bugs before filing issues

    **#bugs-issues** - 在提交问题前获得有关错误的帮助
- 💬 Ask questions in [GitHub Discussions](https://github.com/bmadcode/bmad-method/discussions)

  💬 在 [GitHub Discussions](https://github.com/bmadcode/bmad-method/discussions) 中提问
- 🐛 Report bugs using the [bug report template](https://github.com/bmadcode/bmad-method/issues/new?template=bug_report.md)

  🐛 使用[错误报告模板](https://github.com/bmadcode/bmad-method/issues/new?template=bug_report.md)报告错误
- 💡 Suggest features using the [feature request template](https://github.com/bmadcode/bmad-method/issues/new?template=feature_request.md)

  💡 使用[功能请求模板](https://github.com/bmadcode/bmad-method/issues/new?template=feature_request.md)建议功能
- 📖 Read the full [Contributing Guidelines](../CONTRIBUTING.md)

  📖 阅读完整的[贡献指南](../CONTRIBUTING.md)

## Example: Good vs Bad PRs
## 示例：好的 PR 与坏的 PR

### 😀 Good PR Example
### 😀 好的 PR 示例

**Title**: "Fix broken link to installation guide"

**标题**：“修复安装指南的损坏链接”

**Changes**: One file, one line changed

**更改**：一个文件，一行更改

**Description**: "The link in README.md was pointing to the wrong file. Updated to point to correct installation guide."

**描述**：“README.md 中的链接指向了错误的文件。已更新为指向正确的安装指南。”

### 😞 Bad PR Example
### 😞 坏的 PR 示例

**Title**: "Updates"

**标题**：“更新”

**Changes**: 50 files, entire codebase reformatted

**更改**：50 个文件，整个代码库重新格式化

**Description**: "Made some improvements"

**描述**：“做了一些改进”

---

**Remember**: We're here to help! Don't be afraid to ask questions. Every expert was once a beginner.

**请记住**：我们随时为您提供帮助！不要害怕提问。每个专家都曾是初学者。
