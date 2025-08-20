# Versioning and Releases
# 版本控制与发布

BMad Method uses a simplified release system with manual control and automatic release notes generation.

BMad 方法使用一个简化的发布系统，具有手动控制和自动生成发布说明的功能。

## 🚀 Release Workflow
## 🚀 发布工作流

### Command Line Release (Recommended)
### 命令行发布（推荐）

The fastest way to create a release with beautiful release notes:

创建带有精美发布说明的发布的最快方法：

```bash
# Preview what will be in the release
# 预览发布内容
npm run preview:release

# Create a release
# 创建一个发布
npm run release:patch    # 5.1.0 → 5.1.1 (bug fixes)
                         # 5.1.0 → 5.1.1 (错误修复)
npm run release:minor    # 5.1.0 → 5.2.0 (new features)
                         # 5.1.0 → 5.2.0 (新功能)
npm run release:major    # 5.1.0 → 6.0.0 (breaking changes)
                         # 5.1.0 → 6.0.0 (破坏性变更)

# Watch the release process
# 观察发布过程
npm run release:watch
```

### One-Liner Release
### 单行命令发布

```bash
npm run preview:release && npm run release:minor && npm run release:watch
```

## 📝 What Happens Automatically
## 📝 自动发生什么

When you trigger a release, the GitHub Actions workflow automatically:

当您触发发布时，GitHub Actions 工作流会自动：

1. ✅ **Validates** - Runs tests, linting, and formatting checks
   
   ✅ **验证** - 运行测试、代码风格检查和格式化检查
2. ✅ **Bumps Version** - Updates `package.json` and installer version
   
   ✅ **提升版本** - 更新 `package.json` 和安装程序版本
3. ✅ **Generates Release Notes** - Categorizes commits since last release:
   
   ✅ **生成发布说明** - 对自上次发布以来的提交进行分类：
   - ✨ **New Features** (`feat:`, `Feature:`)

     ✨ **新功能** (`feat:`, `Feature:`)
   - 🐛 **Bug Fixes** (`fix:`, `Fix:`)

     🐛 **错误修复** (`fix:`, `Fix:`)
   - 🔧 **Maintenance** (`chore:`, `Chore:`)

     🔧 **维护** (`chore:`, `Chore:`)
   - 📦 **Other Changes** (everything else)

     📦 **其他变更** (其他所有)
4. ✅ **Creates Git Tag** - Tags the release version
   
   ✅ **创建 Git 标签** - 标记发布版本
5. ✅ **Publishes to NPM** - With `@latest` tag for user installations
   
   ✅ **发布到 NPM** - 带有 `@latest` 标签供用户安装
6. ✅ **Creates GitHub Release** - With formatted release notes
   
   ✅ **创建 GitHub 发布** - 带有格式化的发布说明

## 📋 Sample Release Notes
## 📋 发布说明示例

The workflow automatically generates professional release notes like this:

工作流会自动生成如下专业的发布说明：

````markdown
## 🚀 What's New in v5.2.0
## 🚀 v5.2.0 的新功能

### ✨ New Features
### ✨ 新功能

- feat: add team collaboration mode
- feat: enhance CLI with interactive prompts

### 🐛 Bug Fixes
### 🐛 错误修复

- fix: resolve installation path issues
- fix: handle edge cases in agent loading

### 🔧 Maintenance
### 🔧 维护

- chore: update dependencies
- chore: improve error messages

## 📦 Installation
## 📦 安装

```bash
npx bmad-method install
```
````

**Full Changelog**: https://github.com/bmadcode/BMAD-METHOD/compare/v5.1.0...v5.2.0

**完整变更日志**：https://github.com/bmadcode/BMAD-METHOD/compare/v5.1.0...v5.2.0

````

## 🎯 User Installation
## 🎯 用户安装

After any release, users can immediately get the new version with:
任何发布后，用户都可以立即通过以下方式获取新版本：

```bash
npx bmad-method install    # Always gets latest release
                           # 始终获取最新版本
```

## 📊 Preview Before Release
## 📊 发布前预览

Always preview what will be included in your release:
始终预览您的发布中将包含的内容：

```bash
npm run preview:release
```

This shows:
这将显示：

- Commits since last release
  自上次发布以来的提交

- Categorized changes
  分类后的变更

- Estimated next version
  预计的下一个版本

- Release notes preview
  发布说明预览

## 🔧 Manual Release (GitHub UI)
## 🔧 手动发布 (GitHub UI)

You can also trigger releases through GitHub Actions:
您也可以通过 GitHub Actions 触发发布：

1. Go to **GitHub Actions** → **Manual Release**
   转到 **GitHub Actions** → **Manual Release**

2. Click **"Run workflow"**
   点击 **"Run workflow"**

3. Choose version bump type (patch/minor/major)
   选择版本提升类型 (patch/minor/major)

4. Everything else happens automatically
   其他一切都会自动发生

## 📈 Version Strategy
## 📈 版本策略

- **Patch** (5.1.0 → 5.1.1): Bug fixes, minor improvements
  **补丁** (5.1.0 → 5.1.1): 错误修复，微小改进

- **Minor** (5.1.0 → 5.2.0): New features, enhancements
  **次要** (5.1.0 → 5.2.0): 新功能，增强

- **Major** (5.1.0 → 6.0.0): Breaking changes, major redesigns
  **主要** (5.1.0 → 6.0.0): 破坏性变更，重大重新设计

## 🛠️ Development Workflow
## 🛠️ 开发工作流

1. **Develop Freely** - Merge PRs to main without triggering releases
   **自由开发** - 将 PR 合并到 main 分支而不会触发发布

2. **Test Unreleased Changes** - Clone repo to test latest main branch
   **测试未发布的变更** - 克隆仓库以测试最新的 main 分支

3. **Release When Ready** - Use command line or GitHub Actions to cut releases
   **准备好后发布** - 使用命令行或 GitHub Actions 进行发布

4. **Users Get Updates** - Via simple `npx bmad-method install` command
   **用户获取更新** - 通过简单的 `npx bmad-method install` 命令

This gives you complete control over when releases happen while automating all the tedious parts like version bumping, release notes, and publishing.
这使您可以完全控制发布的时机，同时自动化所有繁琐的部分，如版本提升、发布说明和发布。

## 🔍 Troubleshooting
## 🔍 故障排除

### Check Release Status
### 检查发布状态

```bash
gh run list --workflow="Manual Release"
npm view bmad-method dist-tags
git tag -l | sort -V | tail -5
```

### View Latest Release
### 查看最新发布

```bash
gh release view --web
npm view bmad-method versions --json
```

### If Version Sync Needed
### 如果需要版本同步

If your local files don't match the published version after a release:
如果您的本地文件在发布后与已发布的版本不匹配：

```bash
./tools/sync-version.sh    # Automatically syncs local files with npm latest
                           # 自动将本地文件与 npm 最新版本同步
```

### If Release Fails
### 如果发布失败

- Check GitHub Actions logs: `gh run view <run-id> --log-failed`
  检查 GitHub Actions 日志：`gh run view <run-id> --log-failed`

- Verify NPM tokens are configured
  验证 NPM 令牌是否已配置
  
- Ensure branch protection allows workflow pushes
  确保分支保护允许工作流推送
````
