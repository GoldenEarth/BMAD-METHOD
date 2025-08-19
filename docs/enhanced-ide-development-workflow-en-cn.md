# Enhanced IDE Development Workflow
# 增强型 IDE 开发工作流

This is a simple step-by-step guide to help you efficiently manage your development workflow using the BMad Method. The workflow integrates the Test Architect (QA agent) throughout the development lifecycle to ensure quality, prevent regressions, and maintain high standards. Refer to the **[<ins>User Guide</ins>](user-guide.md)** for any scenario that is not covered here.

这是一个简单的分步指南，旨在帮助您使用 BMad 方法高效地管理开发工作流。该工作流在整个开发生命周期中集成了测试架构师（QA 代理），以确保质量、防止回归并维持高标准。如此处未涵盖任何场景，请参阅**[<ins>用户指南</ins>](user-guide.md)**。

## Create New Branch
## 创建新分支

1. **Start new branch**
   
   **开始新分支**

## Story Creation (Scrum Master)
## 故事创建（Scrum Master）

1. **Start new chat/conversation**
   
   **开始新的聊天/对话**
2. **Load SM agent**
   
   **加载 SM 代理**
3. **Execute**: `*draft` (runs create-next-story task)
   
   **执行**：`*draft`（运行 create-next-story 任务）
4. **Review generated story** in `docs/stories/`
   
   在 `docs/stories/` 中**审查生成的故事**
5. **Update status**: Change from "Draft" to "Approved"
   
   **更新状态**：从“草稿”更改为“已批准”

## Story Implementation (Developer)
## 故事实现（开发人员）

1. **Start new chat/conversation**
   
   **开始新的聊天/对话**
2. **Load Dev agent**
   
   **加载开发代理**
3. **Execute**: `*develop-story {selected-story}` (runs execute-checklist task)
   
   **执行**：`*develop-story {selected-story}`（运行 execute-checklist 任务）
4. **Review generated report** in `{selected-story}`
   
   在 `{selected-story}` 中**审查生成的报告**

## Test Architect Integration Throughout Workflow
## 在整个工作流中集成测试架构师

The Test Architect (Quinn) provides comprehensive quality assurance throughout the development lifecycle. Here's how to leverage each capability at the right time.

测试架构师（Quinn）在整个开发生命周期中提供全面的质量保证。以下是如何在适当的时间利用每项功能的方法。

**Command Aliases:** Documentation uses short forms (`*risk`, `*design`, `*nfr`, `*trace`) for the full commands (`*risk-profile`, `*test-design`, `*nfr-assess`, `*trace-requirements`).

**命令别名：** 文档中使用缩写形式（`*risk`, `*design`, `*nfr`, `*trace`）来代表完整命令（`*risk-profile`, `*test-design`, `*nfr-assess`, `*trace-requirements`）。

### Quick Command Reference
### 快速命令参考

| **Stage**                | **Command** | **Purpose**                             | **Output**                                                      | **Priority**                |
| :----------------------- | :---------- | :-------------------------------------- | :-------------------------------------------------------------- | :-------------------------- |
| **After Story Approval** | `*risk`     | Identify integration & regression risks | `docs/qa/assessments/{epic}.{story}-risk-{YYYYMMDD}.md`         | High for complex/brownfield |
|                          | `*design`   | Create test strategy for dev            | `docs/qa/assessments/{epic}.{story}-test-design-{YYYYMMDD}.md`  | High for new features       |
| **During Development**   | `*trace`    | Verify test coverage                    | `docs/qa/assessments/{epic}.{story}-trace-{YYYYMMDD}.md`        | Medium                      |
|                          | `*nfr`      | Validate quality attributes             | `docs/qa/assessments/{epic}.{story}-nfr-{YYYYMMDD}.md`          | High for critical features  |
| **After Development**    | `*review`   | Comprehensive assessment                | QA Results in story + `docs/qa/gates/{epic}.{story}-{slug}.yml` | **Required**                |
| **Post-Review**          | `*gate`     | Update quality decision                 | Updated `docs/qa/gates/{epic}.{story}-{slug}.yml`               | As needed                   |

| **阶段**             | **命令**    | **目的**                                | **输出**                                                        | **优先级**                  |
| :------------------- | :---------- | :-------------------------------------- | :-------------------------------------------------------------- | :-------------------------- |
| **故事批准后**       | `*risk`     | 识别集成和回归风险                      | `docs/qa/assessments/{epic}.{story}-risk-{YYYYMMDD}.md`         | 对于复杂/棕地项目为高       |
|                      | `*design`   | 为开发人员创建测试策略                  | `docs/qa/assessments/{epic}.{story}-test-design-{YYYYMMDD}.md`  | 对于新功能为高              |
| **开发期间**         | `*trace`    | 验证测试覆盖率                          | `docs/qa/assessments/{epic}.{story}-trace-{YYYYMMDD}.md`        | 中等                        |
|                      | `*nfr`      | 验证质量属性                            | `docs/qa/assessments/{epic}.{story}-nfr-{YYYYMMDD}.md`          | 对于关键功能为高            |
| **开发后**           | `*review`   | 全面评估                                | 故事中的 QA 结果 + `docs/qa/gates/{epic}.{story}-{slug}.yml`    | **必需**                    |
| **审查后**           | `*gate`     | 更新质量决策                            | 更新的 `docs/qa/gates/{epic}.{story}-{slug}.yml`                | 根据需要                    |

### Stage 1: After Story Creation (Before Dev Starts)
### 阶段 1：故事创建后（开发开始前）

**RECOMMENDED - Set Developer Up for Success:**

**推荐 - 为开发人员的成功做好准备：**

```bash
# 1. RISK ASSESSMENT (Run FIRST for complex stories)
# 1. 风险评估（对于复杂故事首先运行）
@qa *risk {approved-story}
# Identifies:
# 识别：
#   - Technical debt impact
#     技术债务影响
#   - Integration complexity
#     集成复杂性
#   - Regression potential (1-9 scoring)
#     回归可能性（1-9分）
#   - Mitigation strategies
#     缓解策略
# Critical for: Brownfield, API changes, data migrations
# 对以下情况至关重要：棕地项目、API 变更、数据迁移

# 2. TEST DESIGN (Run SECOND to guide implementation)
# 2. 测试设计（其次运行以指导实施）
@qa *design {approved-story}
# Provides:
# 提供：
#   - Test scenarios per acceptance criterion
#     每个验收标准的测试场景
#   - Test level recommendations (unit/integration/E2E)
#     测试级别建议（单元/集成/端到端）
#   - Risk-based priorities (P0/P1/P2)
#     基于风险的优先级（P0/P1/P2）
#   - Test data requirements
#     测试数据要求
# Share with Dev: Include in story comments or attach to ticket
# 与开发人员共享：包含在故事评论中或附加到工单
```

### Stage 2: During Development (Mid-Implementation Checkpoints)
### 阶段 2：开发期间（实施中期检查点）

**Developer Self-Service Quality Checks:**

**开发人员自助质量检查：**

```bash
# 3. REQUIREMENTS TRACING (Verify coverage mid-development)
# 3. 需求追踪（在开发中期验证覆盖率）
@qa *trace {story-in-progress}
# Validates:
# 验证：
#   - All acceptance criteria have tests
#     所有验收标准都有测试
#   - No missing test scenarios
#     没有遗漏的测试场景
#   - Appropriate test levels
#     适当的测试级别
#   - Given-When-Then documentation clarity
#     Given-When-Then 文档的清晰度
# Run when: After writing initial tests
# 运行时间：编写初始测试后

# 4. NFR VALIDATION (Check quality attributes)
# 4. 非功能性需求验证（检查质量属性）
@qa *nfr {story-in-progress}
# Assesses:
# 评估：
#   - Security: Authentication, authorization, data protection
#     安全性：认证、授权、数据保护
#   - Performance: Response times, resource usage
#     性能：响应时间、资源使用
#   - Reliability: Error handling, recovery
#     可靠性：错误处理、恢复
#   - Maintainability: Code quality, documentation
#     可维护性：代码质量、文档
# Run when: Before marking "Ready for Review"
# 运行时间：标记为“准备审查”之前
```

### Stage 3: Story Review (Quality Gate Assessment)
### 阶段 3：故事审查（质量门评估）

**REQUIRED - Comprehensive Test Architecture Review:**

**必需 - 全面的测试架构审查：**

**Prerequisite:** All tests green locally; lint & type checks pass.

**先决条件：** 本地所有测试通过；代码风格和类型检查通过。

```bash
# 5. FULL REVIEW (Standard review process)
# 5. 全面审查（标准审查流程）
@qa *review {completed-story}
```

**What Happens During Review:**

**审查期间会发生什么：**

1. **Deep Code Analysis**
   
   **深度代码分析**
   - Architecture pattern compliance

     架构模式合规性
   - Code quality and maintainability

      代码质量和可维护性
   - Security vulnerability scanning

     安全漏洞扫描
   - Performance bottleneck detection

     性能瓶颈检测

2. **Active Refactoring**
   
   **主动重构**
   - Improves code directly when safe

     在安全的情况下直接改进代码
   - Fixes obvious issues immediately

     立即修复明显问题
   - Suggests complex refactoring for dev

     为开发人员建议复杂的重构

3. **Test Validation**
   
   **测试验证**
   - Coverage at all levels (unit/integration/E2E)

     所有级别的覆盖率（单元/集成/端到端）
   - Test quality (no flaky tests, proper assertions)

     测试质量（无不稳定测试，正确的断言）
   - Regression test adequacy

     回归测试的充分性

4. **Gate Decision**
   
   **质量门决策**
   - Creates: `docs/qa/gates/{epic}.{story}-{slug}.yml`

     创建：`docs/qa/gates/{epic}.{story}-{slug}.yml`
   - Adds: QA Results section to story file

     添加：QA 结果部分到故事文件
   - Status: PASS/CONCERNS/FAIL/WAIVED

     状态：通过/关注/失败/豁免

### Stage 4: Post-Review (After Addressing Issues)
### 阶段 4：审查后（解决问题后）

**Update Gate Status After Fixes:**

**修复后更新质量门状态：**

```bash
# 6. GATE UPDATE (Document final decision)
# 6. 质量门更新（记录最终决策）
@qa *gate {reviewed-story}
# Updates: Quality gate with new status
# 更新：带有新状态的质量门
# Use when: After addressing review feedback
# 使用时机：处理审查反馈后
# Documents: What was fixed, what was waived
# 记录：修复了什么，豁免了什么
```

### Understanding Gate Decisions
### 理解质量门决策

| **Status**   | **Meaning**                                  | **Action Required**     | **Can Proceed?** |
| :----------- | :------------------------------------------- | :---------------------- | :--------------- |
| **PASS**     | All critical requirements met                | None                    | ✅ Yes           |
| **CONCERNS** | Non-critical issues found                    | Team review recommended | ⚠️ With caution  |
| **FAIL**     | Critical issues (security, missing P0 tests) | Must fix                | ❌ No            |
| **WAIVED**   | Issues acknowledged and accepted             | Document reasoning      | ✅ With approval |

| **状态**     | **含义**                                     | **需要采取的行动**      | **可以继续吗？** |
| :----------- | :------------------------------------------- | :---------------------- | :--------------- |
| **通过**     | 所有关键需求均已满足                         | 无                      | ✅ 是            |
| **关注**     | 发现非关键问题                               | 建议团队审查            | ⚠️ 谨慎进行    |
| **失败**     | 关键问题（安全、缺少 P0 测试）               | 必须修复                | ❌ 否            |
| **豁免**     | 问题已确认并接受                             | 记录原因                | ✅ 经批准后     |

### Risk-Based Testing Strategy
### 基于风险的测试策略

The Test Architect uses risk scoring to prioritize testing:

测试架构师使用风险评分来确定测试的优先级：

| **Risk Score** | **Calculation**                | **Testing Priority**      | **Gate Impact**          |
| :------------- | :----------------------------- | :------------------------ | :----------------------- |
| **9**          | High probability × High impact | P0 - Must test thoroughly | FAIL if untested         |
| **6**          | Medium-high combinations       | P1 - Should test well     | CONCERNS if gaps         |
| **4**          | Medium combinations            | P1 - Should test          | CONCERNS if notable gaps |
| **2-3**        | Low-medium combinations        | P2 - Nice to have         | Note in review           |
| **1**          | Minimal risk                   | P2 - Minimal              | Note in review           |

| **风险评分** | **计算**                       | **测试优先级**            | **对质量门的影响**       |
| :----------- | :----------------------------- | :------------------------ | :----------------------- |
| **9**        | 高概率 × 高影响                | P0 - 必须彻底测试         | 如果未测试则失败         |
| **6**        | 中高组合                       | P1 - 应良好测试           | 如果有差距则关注         |
| **4**        | 中等组合                       | P1 - 应测试               | 如果有显著差距则关注     |
| **2-3**      | 中低组合                       | P2 - 最好有               | 在审查中注明             |
| **1**        | 风险极小                       | P2 - 最低限度             | 在审查中注明             |

### Special Situations & Best Practices
### 特殊情况和最佳实践

#### High-Risk or Brownfield Stories
#### 高风险或棕地故事

```bash
# ALWAYS run this sequence:
# 始终运行此序列：
@qa *risk {story}    # First - identify dangers
                     # 首先 - 识别危险
@qa *design {story}  # Second - plan defense
                     # 其次 - 规划防御
# Then during dev:
# 然后在开发期间：
@qa *trace {story}   # Verify regression coverage
                     # 验证回归覆盖率
@qa *nfr {story}     # Check performance impact
                     # 检查性能影响
# Finally:
# 最后：
@qa *review {story}  # Deep integration analysis
                     # 深度集成分析
```

#### Complex Integrations
#### 复杂集成

- Run `*trace` multiple times during development

  在开发过程中多次运行 `*trace`
- Focus on integration test coverage

  关注集成测试覆盖率
- Use `*nfr` to validate cross-system performance

  使用 `*nfr` 验证跨系统性能
- Review with extra attention to API contracts

  审查时要特别注意 API 合同

#### Performance-Critical Features
#### 性能关键功能

- Run `*nfr` early and often (not just at review)

  尽早并经常运行 `*nfr`（不仅仅是在审查时）
- Establish performance baselines before changes

  在变更前建立性能基线
- Document acceptable performance degradation

  记录可接受的性能下降
- Consider load testing requirements in `*design`

  在 `*design` 中考虑负载测试要求

### Test Quality Standards Enforced
### 强制执行的测试质量标准

Quinn ensures all tests meet these standards:

Quinn 确保所有测试都符合这些标准：

- **No Flaky Tests**: Proper async handling, explicit waits

  **无不稳定测试**：正确的异步处理，明确的等待
- **No Hard Waits**: Dynamic strategies only (polling, events)

  **无硬等待**：仅使用动态策略（轮询、事件）
- **Stateless**: Tests run independently and in parallel

  **无状态**：测试独立并行运行
- **Self-Cleaning**: Tests manage their own test data

  **自我清理**：测试管理自己的测试数据
- **Appropriate Levels**: Unit for logic, integration for interactions, E2E for journeys

  **适当的级别**：单元测试用于逻辑，集成测试用于交互，端到端测试用于用户旅程
- **Clear Assertions**: Keep assertions in tests, not buried in helpers

  **清晰的断言**：将断言保留在测试中，而不是隐藏在辅助函数中

### Documentation & Audit Trail
### 文档和审计追踪

All Test Architect activities create permanent records:

所有测试架构师的活动都会创建永久记录：

- **Assessment Reports**: Timestamped analysis in `docs/qa/assessments/`

  **评估报告**：在 `docs/qa/assessments/` 中带时间戳的分析
- **Gate Files**: Decision records in `docs/qa/gates/`

  **质量门文件**：在 `docs/qa/gates/` 中的决策记录
- **Story Updates**: QA Results sections in story files

  **故事更新**：故事文件中的 QA 结果部分
- **Traceability**: Requirements to test mapping maintained

  **可追溯性**：维护需求到测试的映射

## Commit Changes and Push
## 提交变更并推送

1. **Commit changes**
   
   **提交变更**
2. **Push to remote**
   
   **推送到远程仓库**

## Complete Development Cycle Flow
## 完整的开发周期流程

### The Full Workflow with Test Architect
### 包含测试架构师的完整工作流

1. **SM**: Create next story → Review → Approve
   
   **SM**：创建下一个故事 → 审查 → 批准
2. **QA (Optional)**: Risk assessment (`*risk`) → Test design (`*design`)
   
   **QA（可选）**：风险评估（`*risk`）→ 测试设计（`*design`）
3. **Dev**: Implement story → Write tests → Complete
   
   **开发**：实现故事 → 编写测试 → 完成
4. **QA (Optional)**: Mid-dev checks (`*trace`, `*nfr`)
   
   **QA（可选）**：开发中期检查（`*trace`, `*nfr`）
5. **Dev**: Mark Ready for Review
   
   **开发**：标记为准备审查
6. **QA (Required)**: Review story (`*review`) → Gate decision
   
   **QA（必需）**：审查故事（`*review`）→ 质量门决策
7. **Dev (If needed)**: Address issues
   
   **开发（如果需要）**：解决问题
8. **QA (If needed)**: Update gate (`*gate`)
   
   **QA（如果需要）**：更新质量门（`*gate`）
9.  **Commit**: All changes
    
   **提交**：所有变更
10. **Push**: To remote
    
    **推送**：到远程仓库
11. **Continue**: Until all features implemented
    
    **继续**：直到所有功能实现

### Quick Decision Guide
### 快速决策指南

**Should I run Test Architect commands?**

**我应该运行测试架构师命令吗？**

| **Scenario**             | **Before Dev**                  | **During Dev**               | **After Dev**                |
| :----------------------- | :------------------------------ | :--------------------------- | :--------------------------- |
| **Simple bug fix**       | Optional                        | Optional                     | Required `*review`           |
| **New feature**          | Recommended `*risk`, `*design`  | Optional `*trace`            | Required `*review`           |
| **Brownfield change**    | **Required** `*risk`, `*design` | Recommended `*trace`, `*nfr` | Required `*review`           |
| **API modification**     | **Required** `*risk`, `*design` | **Required** `*trace`        | Required `*review`           |
| **Performance-critical** | Recommended `*design`           | **Required** `*nfr`          | Required `*review`           |
| **Data migration**       | **Required** `*risk`, `*design` | **Required** `*trace`        | Required `*review` + `*gate` |

| **场景**             | **开发前**                      | **开发中**                   | **开发后**                   |
| :------------------- | :------------------------------ | :--------------------------- | :--------------------------- |
| **简单的错误修复**   | 可选                            | 可选                         | 必需 `*review`               |
| **新功能**           | 推荐 `*risk`, `*design`         | 可选 `*trace`                | 必需 `*review`               |
| **棕地项目变更**     | **必需** `*risk`, `*design`     | 推荐 `*trace`, `*nfr`        | 必需 `*review`               |
| **API 修改**         | **必需** `*risk`, `*design`     | **必需** `*trace`            | 必需 `*review`               |
| **性能关键**         | 推荐 `*design`                  | **必需** `*nfr`              | 必需 `*review`               |
| **数据迁移**         | **必需** `*risk`, `*design`     | **必需** `*trace`            | 必需 `*review` + `*gate`     |

### Success Metrics
### 成功指标

The Test Architect helps achieve:

测试架构师帮助实现：

- **Zero regression defects** in production

  生产环境中**零回归缺陷**
- **100% requirements coverage** with tests

  测试**100%覆盖需求**
- **Clear quality gates** for go/no-go decisions

  用于“通过/不通过”决策的**清晰的质量门**
- **Documented risk acceptance** for technical debt

  为技术债务**记录在案的风险接受**
- **Consistent test quality** across the team

  团队中**一致的测试质量**
- **Shift-left testing** with early risk identification

  通过早期风险识别实现**左移测试**
