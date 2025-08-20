# Working in the Brownfield: A Complete Guide
# 棕地项目工作指南：完整版

> **HIGHLY RECOMMENDED: Use Gemini Web or Gemini CLI for Brownfield Documentation Generation!**
> 
> **强烈推荐：使用 Gemini Web 或 Gemini CLI 生成棕地项目文档！**
>
> Gemini Web's 1M+ token context window or Gemini CLI (when it's working) can analyze your ENTIRE codebase, or critical sections of it, all at once (obviously within reason):
> 
> Gemini Web 的 1M+ token 上下文窗口或 Gemini CLI（在可用时）可以一次性分析您的整个代码库或其关键部分（当然是在合理范围内）：
>
> - Upload via GitHub URL or use gemini cli in the project folder
> 
>   通过 GitHub URL 上传或在项目文件夹中使用 gemini cli
> - If working in the web: use `npx bmad-method flatten` to flatten your project into a single file, then upload that file to your web agent.
> 
>   如果在 Web 环境中工作：使用 `npx bmad-method flatten` 将您的项目扁平化为单个文件，然后将该文件上传到您的 Web 代理。

## What is Brownfield Development?
## 什么是棕地开发？

Brownfield development refers to adding features, fixing bugs, or modernizing existing software projects. Unlike greenfield (new) projects, brownfield work requires understanding existing code, respecting constraints, and ensuring new changes integrate seamlessly without breaking existing functionality.

棕地开发是指在现有软件项目中添加功能、修复错误或进行现代化改造。与绿地（全新）项目不同，棕地工作需要理解现有代码、尊重约束，并确保新变更能够无缝集成，而不会破坏现有功能。

## When to Use BMad for Brownfield
## 何时在棕地项目中使用 BMad

- Add significant new features to existing applications
  
  为现有应用程序添加重要的新功能
- Modernize legacy codebases

  对遗留代码库进行现代化改造
- Integrate new technologies or services
  
  集成新技术或服务
- Refactor complex systems

  重构复杂系统
- Fix bugs that require architectural understanding

  修复需要架构理解的错误
- Document undocumented systems

  为未文档化的系统编写文档

## When NOT to use a Brownfield Flow
## 何时不应使用棕地流程

If you have just completed an MVP with BMad, and you want to continue with post-MVP, its easier to just talk to the PM and ask it to work with you to create a new epic to add into the PRD, shard out the epic, update any architecture documents with the architect, and just go from there.

如果您刚用 BMad 完成了一个 MVP，并希望继续进行后 MVP 阶段的开发，更简单的方法是直接与项目经理（PM）沟通，请求其与您协作创建一个新的史诗（epic）并添加到产品需求文档（PRD）中，然后将该史诗分片，与架构师一起更新任何相关的架构文档，然后从那里继续。

## The Complete Brownfield Workflow
## 完整的棕地工作流

1. **Follow the [<ins>User Guide - Installation</ins>](user-guide.md#installation) steps to setup your agent in the web.**
   
   **遵循[<ins>用户指南 - 安装</ins>](user-guide-en-cn.md#installation)中的步骤在 Web 上设置您的代理。**
2. **Generate a 'flattened' single file of your entire codebase** run: `npx bmad-method flatten`
   
   **生成整个代码库的“扁平化”单文件**，运行：`npx bmad-method flatten`

### Choose Your Approach
### 选择您的方法

#### Approach A: PRD-First (Recommended if adding very large and complex new features, single or multiple epics or massive changes)
#### 方法 A：PRD 优先（推荐用于添加非常庞大和复杂的新功能、单个或多个史诗或大规模变更）

**Best for**: Large codebases, monorepos, or when you know exactly what you want to build

**最适用于**：大型代码库、单一代码库（monorepos），或者当您确切知道要构建什么时

1. **Create PRD First** to define requirements
   
   **首先创建 PRD** 以定义需求
2. **Document only relevant areas** based on PRD needs
   
   根据 PRD 需求**仅文档化相关领域**
3. **More efficient** - avoids documenting unused code
   
   **更高效** - 避免文档化未使用的代码

#### Approach B: Document-First (Good for Smaller Projects)
#### 方法 B：文档优先（适用于较小项目）

**Best for**: Smaller codebases, unknown systems, or exploratory changes

**最适用于**：较小的代码库、未知的系统或探索性变更

1. **Document entire system** first
   
   首先**文档化整个系统**
2. **Create PRD** with full context
   
   在拥有完整上下文的情况下**创建 PRD**
3. **More thorough** - captures everything
   
   **更彻底** - 捕获所有内容

### Approach A: PRD-First Workflow (Recommended)
### 方法 A：PRD 优先工作流（推荐）

#### Phase 1: Define Requirements First
#### 阶段 1：首先定义需求

**In Gemini Web (with your flattened-codebase.xml uploaded):**

**在 Gemini Web 中（上传了您的 flattened-codebase.xml 文件后）：**

```bash
@pm
*create-brownfield-prd
```

The PM will:

项目经理（PM）将会：

- **Ask about your enhancement** requirements
  
  **询问您的增强功能**需求
- **Explore the codebase** to understand current state
  
  **探索代码库**以了解当前状态
- **Identify affected areas** that need documentation
  
  **识别需要文档化的受影响区域**
- **Create focused PRD** with clear scope
  
  **创建范围明确的、重点突出的 PRD**

**Key Advantage**: The PRD identifies which parts of your monorepo/large codebase actually need documentation!

**关键优势**：PRD 能识别出您的单一代码库/大型代码库中哪些部分真正需要文档化！

#### Phase 2: Focused Documentation
#### 阶段 2：重点文档化

**Still in Gemini Web, now with PRD context:**

**仍在 Gemini Web 中，现在有了 PRD 的上下文：**

```bash
@architect
*document-project
```

The architect will:

架构师将会：

- **Ask about your focus** if no PRD was provided
  
  如果没有提供 PRD，则**询问您的关注点**
- **Offer options**: Create PRD, provide requirements, or describe the enhancement
  
  **提供选项**：创建 PRD、提供需求或描述增强功能
- **Reference the PRD/description** to understand scope

  **参考 PRD/描述**以理解范围
- **Focus on relevant modules** identified in PRD or your description

  **专注于 PRD 或您的描述中确定的相关模块**
- **Skip unrelated areas** to keep docs lean

  **跳过不相关的区域**以保持文档精简
- **Generate ONE architecture document** for all environments
  
  为所有环境**生成一份架构文档**

The architect creates:

架构师创建：

- **One comprehensive architecture document** following fullstack-architecture template

  遵循全栈架构模板的**一份综合架构文档**
- **Covers all system aspects** in a single file

  在单个文件中**涵盖所有系统方面**
- **Easy to copy and save** as `docs/architecture.md`

  **易于复制和保存**为 `docs/architecture.md`
- **Can be sharded later** in IDE if desired

  如果需要，**稍后可以在 IDE 中进行分片**

For example, if you say "Add payment processing to user service":

例如，如果您说“为用户服务添加支付处理功能”：

- Documents only: user service, API endpoints, database schemas, payment integrations

  仅文档化：用户服务、API 端点、数据库模式、支付集成
- Creates focused source tree showing only payment-related code paths

  创建仅显示与支付相关的代码路径的重点源码树
- Skips: admin panels, reporting modules, unrelated microservices

  跳过：管理面板、报告模块、不相关的微服务

### Approach B: Document-First Workflow
### 方法 B：文档优先工作流

#### Phase 1: Document the Existing System
#### 阶段 1：文档化现有系统

**Best Approach - Gemini Web with 1M+ Context**:

**最佳方法 - 使用具有 1M+ 上下文的 Gemini Web**：

1. **Go to Gemini Web** (gemini.google.com)
   
   **访问 Gemini Web** (gemini.google.com)
2. **Upload your project**:
   
   **上传您的项目**：
   - **Option A**: Paste your GitHub repository URL directly
  
     **选项 A**：直接粘贴您的 GitHub 仓库 URL
   - **Option B**: Upload your flattened-codebase.xml file
  
     **选项 B**：上传您的 flattened-codebase.xml 文件
3. **Load the architect agent**: Upload `dist/agents/architect.txt`
   
   **加载架构师代理**：上传 `dist/agents/architect.txt`
4. **Run documentation**: Type `*document-project`
   
   **运行文档化**：输入 `*document-project`

The architect will generate comprehensive documentation of everything.

架构师将生成所有内容的综合文档。

#### Phase 2: Plan Your Enhancement
#### 阶段 2：规划您的增强功能

##### Option A: Full Brownfield Workflow (Recommended for Major Changes)
##### 选项 A：完整棕地工作流（推荐用于重大变更）

**1. Create Brownfield PRD**:

**1. 创建棕地 PRD**：

```bash
@pm
*create-brownfield-prd
```

The PM agent will:

项目经理（PM）代理将会：

- **Analyze existing documentation** from Phase 1
  
  **分析阶段 1 的现有文档**
- **Request specific enhancement details** from you

  **向您请求具体的增强功能细节**
- **Assess complexity** and recommend approach

  **评估复杂性**并推荐方法
- **Create epic/story structure** for the enhancement

  为增强功能**创建史诗/故事结构**
- **Identify risks and integration points**

  **识别风险和集成点**

**How PM Agent Gets Project Context**:

**PM 代理如何获取项目上下文**：

- In Gemini Web: Already has full project context from Phase 1 documentation

  在 Gemini Web 中：已从阶段 1 的文档中获得完整的项目上下文
- In IDE: Will ask "Please provide the path to your existing project documentation"

  在 IDE 中：会询问“请提供您现有项目文档的路径”

**Key Prompts You'll Encounter**:

**您将遇到的关键提示**：

- "What specific enhancement or feature do you want to add?"

  “您想添加什么具体的增强功能或特性？”
- "Are there any existing systems or APIs this needs to integrate with?"

  “这需要与任何现有系统或 API 集成吗？”
- "What are the critical constraints we must respect?"

  “我们必须遵守哪些关键约束？”
- "What is your timeline and team size?"

  “您的时间表和团队规模是怎样的？”

**2. Create Brownfield Architecture**:

**2. 创建棕地架构**：

```bash
@architect
*create-brownfield-architecture
```

The architect will:

架构师将会：

- **Review the brownfield PRD**

  **审查棕地 PRD**
- **Design integration strategy**

  **设计集成策略**
- **Plan migration approach** if needed

  如果需要，**规划迁移方法**
- **Identify technical risks**

  **识别技术风险**
- **Define compatibility requirements**

  **定义兼容性要求**

##### Option B: Quick Enhancement (For Focused Changes)
##### 选项 B：快速增强（用于重点变更）

**For Single Epic Without Full PRD**:

**对于没有完整 PRD 的单个史诗**：

```bash
@pm
*create-brownfield-epic
```

Use when:

在以下情况使用：

- Enhancement is well-defined and isolated

  增强功能定义明确且独立
- Existing documentation is comprehensive

  现有文档全面
- Changes don't impact multiple systems

  变更不影响多个系统
- You need quick turnaround

  您需要快速周转

**For Single Story**:

**对于单个故事**：

```bash
@pm
*create-brownfield-story
```

Use when:
在以下情况使用：

- Bug fix or tiny feature

  错误修复或微小功能
- Very isolated change

  非常独立的变更
- No architectural impact

  无架构影响
- Clear implementation path

  清晰的实现路径

### Phase 3: Validate Planning Artifacts
### 阶段 3：验证规划产物

```bash
@po
*execute-checklist-po
```

The PO ensures:

产品负责人（PO）确保：

- Compatibility with existing system

  与现有系统的兼容性
- No breaking changes planned
 
  没有计划中的破坏性变更
- Risk mitigation strategies in place

  风险缓解策略已到位
- Clear integration approach

  清晰的集成方法

### Phase 4: Save and Shard Documents
### 阶段 4：保存和分片文档

1. Save your PRD and Architecture as:
   
   将您的 PRD 和架构保存为：

   docs/prd.md

   docs/architecture.md

   (Note: You can optionally prefix with 'brownfield-' if managing multiple versions)

   (注意：如果管理多个版本，您可以选择使用 'brownfield-' 前缀)
2. Shard your docs:
   
   分片您的文档：

   In your IDE

   在您的 IDE 中

   ```bash
   @po
   shard docs/prd.md
   ```

   ```bash
   @po
   shard docs/architecture.md
   ```

### Phase 5: Transition to Development
### 阶段 5：过渡到开发

**Follow the [<ins>Enhanced IDE Development Workflow</ins>](enhanced-ide-development-workflow.md)**

**遵循[<ins>增强型 IDE 开发工作流</ins>](enhanced-ide-development-workflow-en-cn.md)**

## Brownfield Best Practices
## 棕地项目最佳实践

### 1. Always Document First
### 1. 始终先文档化

Even if you think you know the codebase:

即使您认为自己了解代码库：

- Run `document-project` to capture current state

  运行 `document-project` 以捕获当前状态
- AI agents need this context

  AI 代理需要这个上下文
- Discovers undocumented patterns
  
  发现未文档化的模式

### 2. Respect Existing Patterns
### 2. 尊重现有模式

The brownfield templates specifically look for:

棕地模板专门寻找：

- Current coding conventions

  当前的编码约定
- Existing architectural patterns

  现有的架构模式
- Technology constraints

  技术约束
- Team preferences

  团队偏好

### 3. Plan for Gradual Rollout
### 3. 规划逐步推出

Brownfield changes should:

棕地变更应：

- Support feature flags

  支持功能标志
- Plan rollback strategies

  规划回滚策略
- Include migration scripts

  包含迁移脚本
- Maintain backwards compatibility

  保持向后兼容性

### 4. Test Integration Thoroughly
### 4. 彻底测试集成

#### Why the Test Architect is Critical for Brownfield
#### 为何测试架构师对棕地项目至关重要

In brownfield projects, the Test Architect (Quinn) becomes your safety net against breaking existing functionality. Unlike greenfield where you're building fresh, brownfield requires careful validation that new changes don't destabilize what already works.

在棕地项目中，测试架构师（Quinn）成为您防止破坏现有功能的“安全网”。与从零开始构建的绿地项目不同，棕地项目需要仔细验证新变更不会破坏已有的功能。

#### Brownfield-Specific Testing Challenges
#### 棕地项目特有的测试挑战

The Test Architect addresses unique brownfield complexities:

测试架构师解决了棕地项目独特的复杂性：

| **Challenge**               | **How Test Architect Helps**                      | **Command**         |
| :-------------------------- | :------------------------------------------------ | :------------------ |
| **Regression Risks**        | Identifies which existing features might break    | `*risk`             |
| **Legacy Dependencies**     | Maps integration points and hidden dependencies   | `*trace`            |
| **Performance Degradation** | Validates no slowdown in existing flows           | `*nfr`              |
| **Coverage Gaps**           | Finds untested legacy code that new changes touch | `*design`           |
| **Breaking Changes**        | Detects API/contract violations                   | `*review`           |
| **Migration Safety**        | Validates data transformations and rollback plans | `*risk` + `*review` |

| **挑战**               | **测试架构师如何提供帮助**                      | **命令**            |
| :--------------------- | :---------------------------------------------- | :------------------ |
| **回归风险**           | 识别哪些现有功能可能会被破坏                    | `*risk`             |
| **遗留依赖**           | 映射集成点和隐藏的依赖关系                      | `*trace`            |
| **性能下降**           | 验证现有流程没有变慢                            | `*nfr`              |
| **覆盖率差距**         | 发现新变更触及的未经测试的遗留代码              | `*design`           |
| **破坏性变更**         | 检测 API/合同违规                               | `*review`           |
| **迁移安全**           | 验证数据转换和回滚计划                          | `*risk` + `*review` |

#### Complete Test Architect Workflow for Brownfield
#### 棕地项目的完整测试架构师工作流

##### Stage 1: Before Development (Risk & Strategy)
##### 阶段 1：开发前（风险与策略）

**CRITICAL FOR BROWNFIELD - Run These First:**

**对棕地项目至关重要 - 首先运行这些：**

```bash
# 1. RISK ASSESSMENT (Run IMMEDIATELY after story creation)
# 1. 风险评估（在故事创建后立即运行）
@qa *risk {brownfield-story}
# Identifies: Legacy dependencies, breaking changes, integration points
# 识别：遗留依赖、破坏性变更、集成点
# Output: docs/qa/assessments/{epic}.{story}-risk-{YYYYMMDD}.md
# 输出：docs/qa/assessments/{epic}.{story}-risk-{YYYYMMDD}.md
# Brownfield Focus:
# 棕地项目关注点：
#   - Regression probability scoring
#     回归概率评分
#   - Affected downstream systems
#     受影响的下游系统
#   - Data migration risks
#     数据迁移风险
#   - Rollback complexity
#     回滚复杂性

# 2. TEST DESIGN (After risk assessment)
# 2. 测试设计（风险评估后）
@qa *design {brownfield-story}
# Creates: Regression test strategy + new feature tests
# 创建：回归测试策略 + 新功能测试
# Output: docs/qa/assessments/{epic}.{story}-test-design-{YYYYMMDD}.md
# 输出：docs/qa/assessments/{epic}.{story}-test-design-{YYYYMMDD}.md
# Brownfield Focus:
# 棕地项目关注点：
#   - Existing functionality that needs regression tests
#     需要回归测试的现有功能
#   - Integration test requirements
#     集成测试要求
#   - Performance benchmarks to maintain
#     需要维持的性能基准
#   - Feature flag test scenarios
#     功能标志测试场景
```

##### Stage 2: During Development (Continuous Validation)
##### 阶段 2：开发期间（持续验证）

**Monitor Integration Health While Coding:**

**在编码时监控集成健康状况：**

```bash
# 3. REQUIREMENTS TRACING (Mid-development checkpoint)
# 3. 需求追踪（开发中期检查点）
@qa *trace {brownfield-story}
# Maps: New requirements + existing functionality preservation
# 映射：新需求 + 现有功能保留
# Output: docs/qa/assessments/{epic}.{story}-trace-{YYYYMMDD}.md
# 输出：docs/qa/assessments/{epic}.{story}-trace-{YYYYMMDD}.md
# Brownfield Focus:
# 棕地项目关注点：
#   - Existing features that must still work
#     必须仍然能用的现有功能
#   - New/old feature interactions
#     新旧功能交互
#   - API contract preservation
#     API 合同保留
#   - Missing regression test coverage
#     缺失的回归测试覆盖率

# 4. NFR VALIDATION (Before considering "done")
# 4. 非功能性需求验证（在考虑“完成”之前）
@qa *nfr {brownfield-story}
# Validates: Performance, security, reliability unchanged
# 验证：性能、安全性、可靠性未改变
# Output: docs/qa/assessments/{epic}.{story}-nfr-{YYYYMMDD}.md
# 输出：docs/qa/assessments/{epic}.{story}-nfr-{YYYYMMDD}.md
# Brownfield Focus:
# 棕地项目关注点：
#   - Performance regression detection
#     性能回归检测
#   - Security implications of integrations
#     集成的安全影响
#   - Backward compatibility validation
#     向后兼容性验证
#   - Load/stress on legacy components
#     对遗留组件的负载/压力
```

##### Stage 3: Code Review (Deep Integration Analysis)
##### 阶段 3：代码审查（深度集成分析）

**Comprehensive Brownfield Review:**

**全面的棕地项目审查：**

```bash
# 5. FULL REVIEW (When development complete)
# 5. 全面审查（开发完成时）
@qa *review {brownfield-story}
# Performs: Deep analysis + active refactoring
# 执行：深度分析 + 主动重构
# Outputs:
# 输出：
#   - QA Results in story file
#     QA 结果在故事文件中
#   - Gate file: docs/qa/gates/{epic}.{story}-{slug}.yml
#     质量门禁文件：docs/qa/gates/{epic}.{story}-{slug}.yml
```

The review specifically analyzes:

审查特别分析：

- **API Breaking Changes**: Validates all existing contracts maintained

  **API 破坏性变更**：验证所有现有合同是否得到维护
- **Data Migration Safety**: Checks transformation logic and rollback procedures

  **数据迁移安全**：检查转换逻辑和回滚程序
- **Performance Regression**: Compares against baseline metrics

  **性能回归**：与基线指标进行比较
- **Integration Points**: Validates all touchpoints with legacy code

  **集成点**：验证与遗留代码的所有接触点
- **Feature Flag Logic**: Ensures proper toggle behavior

  **功能标志逻辑**：确保正确的切换行为
- **Dependency Impacts**: Maps affected downstream systems

  **依赖影响**：映射受影响的下游系统

##### Stage 4: Post-Review (Gate Updates)
##### 阶段 4：审查后（质量门禁更新）

```bash
# 6. GATE STATUS UPDATE (After addressing issues)
# 6. 质量门禁状态更新（解决问题后）
@qa *gate {brownfield-story}
# Updates: Quality gate decision after fixes
# 更新：修复后的质量门禁决策
# Output: docs/qa/gates/{epic}.{story}-{slug}.yml
# 输出：docs/qa/gates/{epic}.{story}-{slug}.yml
# Brownfield Considerations:
# 棕地项目考虑因素：
#   - May WAIVE certain legacy code issues
#     可能会豁免某些遗留代码问题
#   - Documents technical debt acceptance
#     记录技术债务的接受情况
#   - Tracks migration progress
#     跟踪迁移进度
```

#### Brownfield-Specific Risk Scoring
#### 棕地项目特定的风险评分

The Test Architect uses enhanced risk scoring for brownfield:

测试架构师对棕地项目使用增强的风险评分：

| **Risk Category**      | **Brownfield Factors**                     | **Impact on Gate**  |
| :--------------------- | :----------------------------------------- | :------------------ |
| **Regression Risk**    | Number of integration points × Age of code | Score ≥9 = FAIL     |
| **Data Risk**          | Migration complexity × Data volume         | Score ≥6 = CONCERNS |
| **Performance Risk**   | Current load × Added complexity            | Score ≥6 = CONCERNS |
| **Compatibility Risk** | API consumers × Contract changes           | Score ≥9 = FAIL     |

| **风险类别**       | **棕地因素**                               | **对质量门禁的影响**  |
| :----------------- | :----------------------------------------- | :------------------ |
| **回归风险**       | 集成点数量 × 代码年龄                      | 分数 ≥9 = 失败      |
| **数据风险**       | 迁移复杂性 × 数据量                        | 分数 ≥6 = 关注      |
| **性能风险**       | 当前负载 × 增加的复杂性                    | 分数 ≥6 = 关注      |
| **兼容性风险**     | API 消费者数量 × 合同变更                  | 分数 ≥9 = 失败      |

#### Brownfield Testing Standards
#### 棕地项目测试标准

Quinn enforces additional standards for brownfield:

Quinn 对棕地项目强制执行额外的标准：

- **Regression Test Coverage**: Every touched legacy module needs tests

  **回归测试覆盖率**：每个接触到的遗留模块都需要测试
- **Performance Baselines**: Must maintain or improve current metrics

  **性能基线**：必须维持或改进当前指标
- **Rollback Procedures**: Every change needs a rollback plan

  **回滚程序**：每个变更都需要一个回滚计划
- **Feature Flags**: All risky changes behind toggles

  **功能标志**：所有有风险的变更都应置于切换开关之后
- **Integration Tests**: Cover all legacy touchpoints

  **集成测试**：覆盖所有遗留接触点
- **Contract Tests**: Validate API compatibility

  **合同测试**：验证 API 兼容性
- **Data Validation**: Migration correctness checks

  **数据验证**：迁移正确性检查

#### Quick Reference: Brownfield Test Commands
#### 快速参考：棕地项目测试命令

| **Scenario**                      | **Commands to Run**                                  | **Order**  | **Why Critical**              |
| :-------------------------------- | :--------------------------------------------------- | :--------- | :---------------------------- |
| **Adding Feature to Legacy Code** | `*risk` → `*design` → `*trace` → `*review`           | Sequential | Map all dependencies first    |
| **API Modification**              | `*risk` → `*design` → `*nfr` → `*review`             | Sequential | Prevent breaking consumers    |
| **Performance-Critical Change**   | `*nfr` early and often → `*review`                   | Continuous | Catch degradation immediately |
| **Data Migration**                | `*risk` → `*design` → `*trace` → `*review` → `*gate` | Full cycle | Ensure data integrity         |
| **Bug Fix in Complex System**     | `*risk` → `*trace` → `*review`                       | Focused    | Prevent side effects          |

| **场景**                      | **要运行的命令**                                     | **顺序**   | **为何关键**                  |
| :---------------------------- | :--------------------------------------------------- | :--------- | :---------------------------- |
| **向遗留代码添加功能**        | `*risk` → `*design` → `*trace` → `*review`           | 顺序       | 首先映射所有依赖项            |
| **API 修改**                  | `*risk` → `*design` → `*nfr` → `*review`             | 顺序       | 防止破坏消费者                |
| **性能关键型变更**            | 尽早并经常运行 `*nfr` → `*review`                    | 持续       | 立即发现性能下降              |
| **数据迁移**                  | `*risk` → `*design` → `*trace` → `*review` → `*gate` | 全周期     | 确保数据完整性                |
| **复杂系统中的错误修复**      | `*risk` → `*trace` → `*review`                       | 重点       | 防止副作用                    |

#### Integration with Brownfield Scenarios
#### 与棕地场景的集成

**Scenario-Specific Guidance:**

**特定场景指南：**

1. **Legacy Code Modernization**

   **遗留代码现代化**
   - Start with `*risk` to map all dependencies

     从 `*risk` 开始，映射所有依赖项
   - Use `*design` to plan strangler fig approach

     使用 `*design` 规划绞杀榕（strangler fig）方法（注：绞杀榕方法核心思想是渐进替换，而非推翻重来）
   - Run `*trace` frequently to ensure nothing breaks

     频繁运行 `*trace` 以确保没有东西被破坏
   - `*review` with focus on gradual migration

     `*review` 专注于逐步迁移

2. **Adding Features to Monolith**

   **向单体应用添加功能**
   - `*risk` identifies integration complexity

     `*risk` 识别集成复杂性
   - `*design` plans isolation strategies

     `*design` 规划隔离策略
   - `*nfr` monitors performance impact

     `*nfr` 监控性能影响
   - `*review` validates no monolith degradation

     `*review` 验证单体应用性能未下降

3. **Microservice Extraction**

   **微服务提取**
   - `*risk` maps service boundaries

     `*risk` 映射服务边界
   - `*trace` ensures functionality preservation

     `*trace` 确保功能保留
   - `*nfr` validates network overhead acceptable

     `*nfr` 验证网络开销是否可接受
   - `*gate` documents accepted trade-offs

     `*gate` 记录接受的权衡

4. **Database Schema Changes**

   **数据库模式变更**
   - `*risk` assesses migration complexity

     `*risk` 评估迁移复杂性
   - `*design` plans backward-compatible approach

     `*design` 规划向后兼容的方法
   - `*trace` maps all affected queries

     `*trace` 映射所有受影响的查询
   - `*review` validates migration safety

     `*review` 验证迁移安全性

### 5. Communicate Changes
### 5. 沟通变更

Document:
文档化：

- What changed and why

  变更了什么以及为什么变更
- Migration instructions

  迁移说明
- New patterns introduced

  引入的新模式
- Deprecation notices

  弃用通知

## Common Brownfield Scenarios
## 常见的棕地场景

### Scenario 1: Adding a New Feature
### 场景 1：添加新功能

1. Document existing system
   
   文档化现有系统
2. Create brownfield PRD focusing on integration
   
   创建专注于集成的棕地 PRD
3. **Test Architect Early Involvement**:
   
   **测试架构师早期参与**：
   - Run `@qa *risk` on draft stories to identify integration risks

     在故事草稿上运行 `@qa *risk` 以识别集成风险
   - Use `@qa *design` to plan regression test strategy

     使用 `@qa *design` 规划回归测试策略
4. Architecture emphasizes compatibility
   
   架构强调兼容性
5. Stories include integration tasks with test requirements
   
   故事包括带有测试要求的集成任务
6. **During Development**:
   
   **开发期间**：
   - Developer runs `@qa *trace` to verify coverage

     开发人员运行 `@qa *trace` 以验证覆盖率
   - Use `@qa *nfr` to monitor performance impact

     使用 `@qa *nfr` 监控性能影响
7. **Review Stage**: `@qa *review` validates integration safety
   
   **审查阶段**：`@qa *review` 验证集成安全性

### Scenario 2: Modernizing Legacy Code
### 场景 2：现代化遗留代码

1. Extensive documentation phase
   
   广泛的文档化阶段
2. PRD includes migration strategy
   
   PRD 包括迁移策略
3. **Test Architect Strategy Planning**:
   
   **测试架构师策略规划**：
   - `@qa *risk` assesses modernization complexity

     `@qa *risk` 评估现代化复杂性
   - `@qa *design` plans parallel testing approach

     `@qa *design` 规划并行测试方法
4. Architecture plans gradual transition (strangler fig pattern)
   
   架构规划逐步过渡（绞杀榕模式）
5. Stories follow incremental modernization with:
   
   故事遵循增量现代化，并包含：
   - Regression tests for untouched legacy code

     对未触及的遗留代码进行回归测试
   - Integration tests for new/old boundaries

     对新旧边界进行集成测试
   - Performance benchmarks at each stage

     每个阶段的性能基准
6. **Continuous Validation**: Run `@qa *trace` after each increment
   
   **持续验证**：每次增量后运行 `@qa *trace`
7. **Gate Management**: Use `@qa *gate` to track technical debt acceptance
   
   **质量门禁管理**：使用 `@qa *gate` 跟踪技术债务的接受情况

### Scenario 3: Bug Fix in Complex System
### 场景 3：复杂系统中的错误修复

1. Document relevant subsystems
   
   文档化相关子系统
2. Use `create-brownfield-story` for focused fix
   
   使用 `create-brownfield-story` 进行重点修复
3. **Test Architect Risk Assessment**: Run `@qa *risk` to identify side effect potential
   
   **测试架构师风险评估**：运行 `@qa *risk` 以识别潜在的副作用
4. Include regression test requirements from `@qa *design` output
   
   包含来自 `@qa *design` 输出的回归测试要求
5. **During Fix**: Use `@qa *trace` to map affected functionality
   
   **修复期间**：使用 `@qa *trace` 映射受影响的功能
6. **Before Commit**: Run `@qa *review` for comprehensive validation
   
   **提交前**：运行 `@qa *review` 进行全面验证
7. Test Architect validates no side effects using:
   
   测试架构师使用以下方法验证没有副作用：
   - Risk profiling for side effect analysis (probability × impact scoring)

     用于副作用分析的风险画像（概率 × 影响评分）
   - Trace matrix to ensure fix doesn't break related features

     追踪矩阵以确保修复不会破坏相关功能
   - NFR assessment to verify performance/security unchanged

     非功能性需求评估以验证性能/安全性未改变
   - Gate decision documents fix safety

     质量门禁决策文档记录修复的安全性

### Scenario 4: API Integration
### 场景 4：API 集成

1. Document existing API patterns
   
   文档化现有 API 模式
2. PRD defines integration requirements
   
   PRD 定义集成要求
3. **Test Architect Contract Analysis**:
   
   **测试架构师合同分析**：
   - `@qa *risk` identifies breaking change potential

     `@qa *risk` 识别潜在的破坏性变更
   - `@qa *design` creates contract test strategy

     `@qa *design` 创建合同测试策略
4. Architecture ensures consistent patterns
   
   架构确保一致的模式
5. **API Testing Focus**:
   
   **API 测试重点**：
   - Contract tests for backward compatibility

     用于向后兼容性的合同测试
   - Integration tests for new endpoints

     对新端点的集成测试
   - Performance tests for added load

     对增加的负载进行性能测试
6. Stories include API documentation updates
   
   故事包括 API 文档更新
7. **Validation Checkpoints**:
   
   **验证检查点**：
   - `@qa *trace` maps all API consumers

     `@qa *trace` 映射所有 API 消费者
   - `@qa *nfr` validates response times

     `@qa *nfr` 验证响应时间
   - `@qa *review` ensures no breaking changes

     `@qa *review` 确保没有破坏性变更
8. **Gate Decision**: Document any accepted breaking changes with migration path
   
   **质量门禁决策**：记录任何已接受的破坏性变更及其迁移路径

## Troubleshooting
## 故障排除

### "The AI doesn't understand my codebase"
### “AI 不理解我的代码库”

**Solution**: Re-run `document-project` with more specific paths to critical files

**解决方案**：使用更具体的关键文件路径重新运行 `document-project`

### "Generated plans don't fit our patterns"
### “生成的计划不符合我们的模式”

**Solution**: Update generated documentation with your specific conventions before planning phase

**解决方案**：在规划阶段之前，用您的特定约定更新生成的文档

### "Too much boilerplate for small changes"
### “对于小变更来说，样板代码太多”

**Solution**: Use `create-brownfield-story` instead of full workflow

**解决方案**：使用 `create-brownfield-story` 而不是完整的工作流

### "Integration points unclear"
### “集成点不清晰”

**Solution**: Provide more context during PRD creation, specifically highlighting integration systems

**解决方案**：在 PRD 创建期间提供更多上下文，特别突出集成系统

## Quick Reference
## 快速参考

### Brownfield-Specific Commands
### 棕地项目特定命令

```bash
# Document existing project
# 文档化现有项目
@architect *document-project

# Create enhancement PRD
# 创建增强功能 PRD
@pm *create-brownfield-prd

# Create architecture with integration focus
# 创建以集成为重点的架构
@architect *create-brownfield-architecture

# Quick epic creation
# 快速创建史诗
@pm *create-brownfield-epic

# Single story creation
# 创建单个故事
@pm *create-brownfield-story
```

### Test Architect Commands for Brownfield
### 用于棕地项目的测试架构师命令

Note: Short forms shown below. Full commands: `*risk-profile`, `*test-design`, `*nfr-assess`, `*trace-requirements`

注意：下面显示的是缩写形式。完整命令：`*risk-profile`, `*test-design`, `*nfr-assess`, `*trace-requirements`

```bash
# BEFORE DEVELOPMENT (Planning)
# 开发前（规划）
@qa *risk {story}     # Assess regression & integration risks
                      # 评估回归和集成风险
@qa *design {story}   # Plan regression + new feature tests
                      # 规划回归 + 新功能测试

# DURING DEVELOPMENT (Validation)
# 开发期间（验证）
@qa *trace {story}    # Verify coverage of old + new
                      # 验证新旧代码的覆盖率
@qa *nfr {story}      # Check performance degradation
                      # 检查性能下降

# AFTER DEVELOPMENT (Review)
# 开发后（审查）
@qa *review {story}   # Deep integration analysis
                      # 深度集成分析
@qa *gate {story}     # Update quality decision
                      # 更新质量决策
```

### Decision Tree
### 决策树

```text
Do you have a large codebase or monorepo?
您有一个大型代码库或单一代码库吗？
├─ Yes → PRD-First Approach
│  是 → PRD 优先方法
│   └─ Create PRD → Document only affected areas
│      创建 PRD → 仅文档化受影响的区域
└─ No → Is the codebase well-known to you?
   否 → 您对代码库熟悉吗？
    ├─ Yes → PRD-First Approach
    │  是 → PRD 优先方法
    └─ No → Document-First Approach
       否 → 文档优先方法

Is this a major enhancement affecting multiple systems?
这是一个影响多个系统的重大增强吗？
├─ Yes → Full Brownfield Workflow
│  是 → 完整棕地工作流
│   └─ ALWAYS run Test Architect *risk + *design first
│      始终首先运行测试架构师的 *risk + *design
└─ No → Is this more than a simple bug fix?
   否 → 这不仅仅是一个简单的错误修复吗？
    ├─ Yes → *create-brownfield-epic
    │  是 → *create-brownfield-epic
    │   └─ Run Test Architect *risk for integration points
    │      为集成点运行测试架构师的 *risk
    └─ No → *create-brownfield-story
       否 → *create-brownfield-story
        └─ Still run *risk if touching critical paths
           如果触及关键路径，仍然运行 *risk

Does the change touch legacy code?
变更是否触及遗留代码？
├─ Yes → Test Architect is MANDATORY
│  是 → 测试架构师是强制性的
│   ├─ *risk → Identify regression potential
│   │  *risk → 识别回归可能性
│   ├─ *design → Plan test coverage
│   │  *design → 规划测试覆盖率
│   └─ *review → Validate no breakage
│      *review → 验证没有破坏
└─ No → Test Architect is RECOMMENDED
   否 → 推荐使用测试架构师
    └─ *review → Ensure quality standards
       *review → 确保质量标准
```

## Conclusion
## 结论

Brownfield development with BMad Method provides structure and safety when modifying existing systems. The Test Architect becomes your critical safety net, using risk assessment, regression testing, and continuous validation to ensure new changes don't destabilize existing functionality.

使用 BMad 方法进行棕地开发，在修改现有系统时提供了结构和安全性。测试架构师成为您关键的安全网，通过风险评估、回归测试和持续验证，确保新变更不会破坏现有功能的稳定性。

**The Brownfield Success Formula:**

**棕地项目成功公式：**

1. **Document First** - Understand what exists
   
   **首先文档化** - 了解现有情况
2. **Assess Risk Early** - Use Test Architect `*risk` before coding
   
   **尽早评估风险** - 编码前使用测试架构师的 `*risk`
3. **Plan Test Strategy** - Design regression + new feature tests
   
   **规划测试策略** - 设计回归测试 + 新功能测试
4. **Validate Continuously** - Check integration health during development
   
   **持续验证** - 开发期间检查集成健康状况
5. **Review Comprehensively** - Deep analysis before committing
   
   **全面审查** - 提交前进行深度分析
6. **Gate Decisively** - Document quality decisions
   
   **果断设门** - 记录质量决策

Remember: **In brownfield, the Test Architect isn't optional - it's your insurance policy against breaking production.**

请记住：**在棕地项目中，测试架构师不是可选项——它是您防止破坏生产环境的保险。**
