# BMad Method Guiding Principles
# BMad 方法指导原则

The BMad Method is a natural language framework for AI-assisted software development. These principles ensure contributions maintain the method's effectiveness.

BMad 方法是一个用于 AI 辅助软件开发的自然语言框架。这些原则确保贡献能够保持该方法的有效性。

## Core Principles
## 核心原则

### 1. Dev Agents Must Be Lean
### 1. 开发代理必须精简

- **Minimize dev agent dependencies**: Development agents that work in IDEs must have minimal context overhead

  **最小化开发代理依赖**：在 IDE 中工作的开发代理必须有最小的上下文开销
- **Save context for code**: Every line counts - dev agents should focus on coding, not documentation

  **为代码保留上下文**：每一行都很重要 - 开发代理应专注于编码，而不是文档
- **Web agents can be larger**: Planning agents (PRD Writer, Architect) used in web UI can have more complex tasks and dependencies

  **Web 代理可以更大**：在 Web UI 中使用的规划代理（PRD 编写者、架构师）可以有更复杂的任务和依赖
- **Small files, loaded on demand**: Multiple small, focused files are better than large files with many branches

  **小文件，按需加载**：多个小的、专注的文件优于具有许多分支的大文件

### 2. Natural Language First
### 2. 自然语言优先

- **Everything is markdown**: Agents, tasks, templates - all written in plain English

  **一切皆为 markdown**：代理、任务、模板 - 全部用纯英文编写
- **No code in core**: The framework itself contains no programming code, only natural language instructions

  **核心无代码**：框架本身不包含任何编程代码，只有自然语言指令
- **Self-contained templates**: Templates are defined as YAML files with structured sections that include metadata, workflow configuration, and detailed instructions for content generation

  **自包含模板**：模板被定义为具有结构化部分的 YAML 文件，其中包括元数据、工作流配置和内容生成的详细说明

### 3. Agent and Task Design
### 3. 代理与任务设计

- **Agents define roles**: Each agent is a persona with specific expertise (e.g., Frontend Developer, API Developer)

  **代理定义角色**：每个代理都是一个具有特定专业知识的角色（例如，前端开发人员、API 开发人员）
- **Tasks are procedures**: Step-by-step instructions an agent follows to complete work

  **任务是程序**：代理为完成工作而遵循的逐步说明
- **Templates are outputs**: Structured documents with embedded instructions for generation

  **模板是输出**：带有嵌入式生成说明的结构化文档
- **Dependencies matter**: Explicitly declare only what's needed

  **依赖关系很重要**：只明确声明需要的内容

## Practical Guidelines
## 实践指南

### When to Add to Core
### 何时添加到核心

- Universal software development needs only

  仅限通用软件开发需求
- Doesn't bloat dev agent contexts

  不会臃肿开发代理的上下文
- Follows existing agent/task/template patterns

  遵循现有的代理/任务/模板模式

### When to Create Expansion Packs
### 何时创建扩展包

- Domain-specific needs beyond software development

  超出软件开发的领域特定需求
- Non-technical domains (business, wellness, education, creative)

  非技术领域（商业、健康、教育、创意）
- Specialized technical domains (games, infrastructure, mobile)

  专业技术领域（游戏、基础设施、移动）
- Heavy documentation or knowledge bases

  大量文档或知识库
- Anything that would bloat core agents

  任何会使核心代理臃肿的东西

See [Expansion Packs Guide](../docs/expansion-packs.md) for detailed examples and ideas.

有关详细示例和想法，请参阅[扩展包指南](../docs/expansion-packs-en-cn.md)。

### Agent Design Rules
### 代理设计规则

1. **Web/Planning Agents**: Can have richer context, multiple tasks, extensive templates
   
   **Web/规划代理**：可以有更丰富的上下文、多个任务、广泛的模板
2. **Dev Agents**: Minimal dependencies, focused on code generation, lean task sets
   
   **开发代理**：最小的依赖关系，专注于代码生成，精简的任务集
3. **All Agents**: Clear persona, specific expertise, well-defined capabilities
   
   **所有代理**：清晰的角色、特定的专业知识、明确定义的能力

### Task Writing Rules
### 任务编写规则

1. Write clear step-by-step procedures
   
   编写清晰的逐步程序
2. Use markdown formatting for readability
   
   使用 markdown 格式以提高可读性
3. Keep dev agent tasks focused and concise
   
   保持开发代理任务的专注和简洁
4. Planning tasks can be more elaborate
   
   规划任务可以更详尽
5. **Prefer multiple small tasks over one large branching task**
   
   **倾向于多个小任务，而不是一个大的分支任务**
   - Instead of one task with many conditional paths

     而不是一个有许多条件路径的任务
   - Create multiple focused tasks the agent can choose from

     创建多个专注的任务供代理选择
   - This keeps context overhead minimal

     这使上下文开销保持最小
6. **Reuse common tasks** - Don't create new document creation tasks
   
   **重用通用任务** - 不要创建新的文档创建任务
   - Use the existing `create-doc` task

     使用现有的 `create-doc` 任务
   - Pass the appropriate YAML template with structured sections

     传递带有结构化部分的适当 YAML 模板
   - This maintains consistency and reduces duplication

     这保持了一致性并减少了重复

### Template Rules
### 模板规则

Templates follow the [BMad Document Template](../common/utils/bmad-doc-template.md) specification using YAML format:

模板遵循使用 YAML 格式的 [BMad 文档模板](../common/utils/bmad-doc-template.md) 规范：

1. **Structure**: Templates are defined in YAML with clear metadata, workflow configuration, and section hierarchy
   
   **结构**：模板在 YAML 中定义，具有清晰的元数据、工作流配置和节层次结构
2. **Separation of Concerns**: Instructions for LLMs are in `instruction` fields, separate from content
   
   **关注点分离**：给 LLM 的指令在 `instruction` 字段中，与内容分开
3. **Reusability**: Templates are agent-agnostic and can be used across different agents
   
   **可重用性**：模板与代理无关，可以在不同的代理中使用
4. **Key Components**:
   
   **关键组件**：
   - `template` block for metadata (id, name, version, output settings)

     用于元数据（id、名称、版本、输出设置）的 `template` 块
   - `workflow` block for interaction mode configuration

     用于交互模式配置的 `workflow` 块
   - `sections` array defining document structure with nested subsections

     定义带有嵌套子部分的文档结构的 `sections` 数组
   - Each section has `id`, `title`, and `instruction` fields

     每个部分都有 `id`、`title` 和 `instruction` 字段
5. **Advanced Features**:
   
   **高级功能**：
   - Variable substitution using `{{variable_name}}` syntax

     使用 `{{variable_name}}` 语法的变量替换
   - Conditional sections with `condition` field

     带有 `condition` 字段的条件部分
   - Repeatable sections with `repeatable: true`

     带有 `repeatable: true` 的可重复部分
   - Agent permissions with `owner` and `editors` fields

     带有 `owner` 和 `editors` 字段的代理权限
   - Examples arrays for guidance (never included in output)

     用于指导的示例数组（从不包含在输出中）
6. **Clean Output**: YAML structure ensures all processing logic stays separate from generated content
   
   **干净的输出**：YAML 结构确保所有处理逻辑与生成的内容分离

## Remember
## 请记住

- The power is in natural language orchestration, not code

  力量在于自然语言编排，而不是代码
- Dev agents code, planning agents plan

  开发代理编码，规划代理规划
- Keep dev agents lean for maximum coding efficiency

  保持开发代理精简以实现最大的编码效率
- Expansion packs handle specialized domains

  扩展包处理专业领域
