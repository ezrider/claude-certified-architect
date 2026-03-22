# Claude 认证架构师 — 基础认证

## 学习指南（基于官方考试指南）

---

## 简介

**Claude 认证架构师 — 基础**认证证明专家能够在实施基于 Claude 的实际解决方案时做出合理的权衡决策。考试评估 Claude Code、Claude Agent SDK、Claude API 和模型上下文协议（MCP）的基础知识——这些是使用 Claude 构建生产应用的核心技术。

考题基于真实的行业场景：构建客户支持代理系统、设计多代理研究管道、将 Claude Code 集成到 CI/CD、创建开发者生产力工具，以及从非结构化文档中提取结构化数据。

---

## 目标候选人

理想候选人是**解决方案架构师**，负责设计和交付基于 Claude 的生产应用。您应具备至少 6 个月的实践经验，涵盖：

- **Claude Agent SDK** — 多代理编排、委派子代理、工具集成、生命周期钩子
- **Claude Code** — CLAUDE.md、MCP 服务器、Agent 技能、规划模式
- **模型上下文协议（MCP）** — 用于后端集成的工具和资源
- **提示工程** — JSON 模式、少样本示例、数据提取模板
- **上下文窗口** — 处理长文档、多代理上下文传递
- **CI/CD 管道** — 自动代码审查、测试生成
- **升级与可靠性** — 错误处理、人在回路

---

## 考试格式

| 参数 | 值 |
|---|---|
| 题型 | 单选题（4 选 1） |
| 评分 | 100–1000 分制，及格分数 **720 分** |
| 猜测惩罚 | 无（请回答每道题！） |
| 场景 | 从 6 个可能场景中随机抽取 4 个 |

---

## 考试内容：5 个领域

| 领域 | 权重 |
|---|---|
| 1. 代理架构与编排 | **27%** |
| 2. 工具设计与 MCP 集成 | **18%** |
| 3. Claude Code 配置与工作流 | **20%** |
| 4. 提示工程与结构化输出 | **20%** |
| 5. 上下文管理与可靠性 | **15%** |

---

## 考试场景

### 场景 1：客户支持代理
使用 Claude Agent SDK 构建一个处理退货、账单纠纷和账户问题的代理。该代理使用 MCP 工具（`get_customer`、`lookup_order`、`process_refund`、`escalate_to_human`）。目标是 80% 以上的首次联系解决率和适当的升级处理。

### 场景 2：使用 Claude Code 生成代码
使用 Claude Code 加速开发：代码生成、重构、调试、文档编写。需要将其与自定义斜杠命令和 CLAUDE.md 配置集成，并了解何时使用规划模式。

### 场景 3：多代理研究系统
协调代理将任务委派给专业子代理：网络研究、文档分析、综合和报告生成。系统必须生成带有引用的完整报告。

### 场景 4：开发者生产力工具
代理帮助工程师探索陌生代码库、生成样板代码并自动化日常任务。使用内置工具（Read、Write、Bash、Grep、Glob）和 MCP 服务器。

### 场景 5：用于持续集成的 Claude Code
将 Claude Code 集成到 CI/CD 管道中，用于自动代码审查、测试生成和拉取请求反馈。提示必须设计为最小化误报。

### 场景 6：结构化数据提取
系统从非结构化文档中提取信息，用 JSON 模式验证输出，并保持高精度。必须正确处理边缘情况。

---

# 官方文档

| 资源 | URL |
|---|---|
| **Claude API — Messages** | https://platform.claude.com/docs/en/api/messages |
| **Claude API — Tool Use** | https://platform.claude.com/docs/en/build-with-claude/tool-use |
| **Claude API — Message Batches** | https://platform.claude.com/docs/en/build-with-claude/message-batches |
| **Claude Agent SDK — 概述** | https://platform.claude.com/docs/en/agent-sdk/overview |
| **Claude Agent SDK — Hooks** | https://platform.claude.com/docs/en/agent-sdk/hooks |
| **Claude Agent SDK — Subagents** | https://platform.claude.com/docs/en/agent-sdk/subagents |
| **Claude Agent SDK — Sessions** | https://platform.claude.com/docs/en/agent-sdk/sessions |
| **模型上下文协议（MCP）** | https://modelcontextprotocol.io/ |
| **MCP — Tools** | https://modelcontextprotocol.io/docs/concepts/tools |
| **MCP — Resources** | https://modelcontextprotocol.io/docs/concepts/resources |
| **MCP — Servers** | https://modelcontextprotocol.io/docs/concepts/servers |
| **Claude Code — 文档** | https://code.claude.com/docs/en/overview |
| **Claude Code — CLAUDE.md 与内存** | https://code.claude.com/docs/en/memory |
| **Claude Code — 技能（含斜杠命令）** | https://code.claude.com/docs/en/skills |
| **Claude Code — Hooks** | https://code.claude.com/docs/en/hooks |
| **Claude Code — 子代理** | https://code.claude.com/docs/en/sub-agents |
| **Claude Code — MCP 集成** | https://code.claude.com/docs/en/mcp |
| **Claude Code — GitHub Actions CI/CD** | https://code.claude.com/docs/en/github-actions |
| **Claude Code — GitLab CI/CD** | https://code.claude.com/docs/en/gitlab-ci-cd |
| **Claude Code — 无头模式（非交互式）** | https://code.claude.com/docs/en/headless |
| **提示工程指南** | https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview |
| **扩展思维** | https://platform.claude.com/docs/en/build-with-claude/extended-thinking |
| **Anthropic Cookbook（代码示例）** | https://github.com/anthropics/anthropic-cookbook |

---

# 第一部分：理论基础

本部分涵盖成功通过考试所需的全部理论知识。内容按技术和概念组织，而非按考试领域划分——这有助于您对每个主题建立更深入的理解。

---

# 第 1 章：Claude API — 模型交互基础

> 文档：[Messages API](https://platform.claude.com/docs/en/api/messages) | [提示工程](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview)

## 1.1 API 请求结构

Claude API 遵循请求-响应模型。对 Claude Messages API 的每个请求包含：

```json
{
  "model": "claude-sonnet-4-6",
  "max_tokens": 1024,
  "system": "你是一个有帮助的助手。",
  "messages": [
    {"role": "user", "content": "你好！"},
    {"role": "assistant", "content": "你好！"},
    {"role": "user", "content": "你好吗？"}
  ],
  "tools": [...],
  "tool_choice": {"type": "auto"}
}
```

**关键字段：**
- `model` — 模型选择（`claude-opus-4-6`、`claude-sonnet-4-6`、`claude-haiku-4-5`）
- `max_tokens` — 响应中的最大令牌数
- `system` — 系统提示（定义模型行为）
- `messages` — 对话历史（**必须发送完整历史**以保持连贯性）
- `tools` — 可用工具的定义
- `tool_choice` — 工具选择策略

## 1.2 消息角色

`messages` 数组使用三种角色：
- `user` — 用户消息
- `assistant` — 模型响应（发送历史时包含）
- `tool` — 工具调用结果（角色未明确设置；以 `tool_result` 内容块的形式出现）

**至关重要：** 每次 API 请求都必须发送**完整的对话历史**。模型不会在请求之间保持状态——每次调用都是独立的。

## 1.3 响应中的 `stop_reason` 字段

Claude API 响应包含 `stop_reason`，表示模型停止生成的原因：

| 值 | 描述 | 操作 |
|---|---|---|
| `"end_turn"` | 模型完成了响应 | 向用户显示结果 |
| `"tool_use"` | 模型想要调用工具 | 执行工具并返回结果 |
| `"max_tokens"` | 达到令牌限制 | 响应被截断；可能需要增加限制 |
| `"stop_sequence"` | 遇到停止序列 | 根据应用程序逻辑处理 |

对于代理系统，`"tool_use"` 和 `"end_turn"` 最为重要——它们控制代理循环。

## 1.4 系统提示

系统提示是定义上下文和行为规则的特殊指令。它：
- 不是 `messages` 数组的一部分；通过 `system` 字段单独传递
- 优先于用户消息
- 一次加载，在整个对话中有效
- 用于定义角色、约束和输出格式

**考试重点：** 系统提示的措辞可能创建意外的工具关联。例如，"始终验证客户"之类的指令可能导致模型过度使用 `get_customer`，即使在不必要的时候。

## 1.5 上下文窗口

上下文窗口是模型一次可以处理的文本总量（以令牌为单位）。它包括：
- 系统提示
- 完整的消息历史
- 工具定义
- 工具结果

**主要上下文窗口问题：**

1. **中间丢失效应：** 模型可靠地处理长输入开头和结尾的信息，但可能遗漏中间的细节。缓解方法：将关键信息放在开头或结尾附近。

2. **工具结果积累：** 每次工具调用都会将输出添加到上下文中。如果工具返回 40 多个字段但只需要 5 个，大部分上下文就被浪费了。

3. **渐进式摘要：** 压缩历史时，数值、百分比和日期往往丢失，变成模糊的表达（"大约"、"差不多"、"几个"）。

---

# 第 2 章：工具与 `tool_use`

> 文档：[Tool Use](https://platform.claude.com/docs/en/build-with-claude/tool-use)

## 2.1 什么是 `tool_use`

`tool_use` 是允许 Claude 调用外部函数的机制。模型不直接运行代码——它生成结构化的工具调用请求；您的代码执行它并返回结果。

## 2.2 工具定义

每个工具使用 JSON 模式定义：

```json
{
  "name": "get_customer",
  "description": "通过邮箱或 ID 查找客户。返回客户档案，包括姓名、邮箱、订单历史和账户状态。使用此工具之前请先于 lookup_order 前验证客户身份。接受邮箱（格式：user@domain.com）或数字 customer_id。",
  "input_schema": {
    "type": "object",
    "properties": {
      "email": {"type": "string", "description": "客户邮箱"},
      "customer_id": {"type": "integer", "description": "数字客户 ID"}
    },
    "required": []
  }
}
```

**工具描述的关键要素：**

1. **描述是主要选择机制。** LLM 根据工具描述选择工具。最简描述（"获取客户信息"）在工具重叠时会导致错误。

2. **描述中应包含：**
   - 工具的功能和返回内容
   - 输入格式和示例值
   - 边缘情况和约束
   - 何时使用此工具而非类似替代品

3. **避免** 跨工具使用相同或重叠的描述。如果 `analyze_content` 和 `analyze_document` 描述几乎相同，模型会混淆它们。

4. **内置工具与 MCP 工具：** 代理可能更偏好内置工具（Read、Grep）而非功能类似的 MCP 工具。为防止这种情况，需强化 MCP 工具描述——突出内置工具无法提供的具体优势、独特数据或上下文。

## 2.3 `tool_choice` 参数

`tool_choice` 控制模型如何选择工具：

| 值 | 行为 | 使用时机 |
|---|---|---|
| `{"type": "auto"}` | 模型决定是否调用工具或用文本回答 | 大多数情况的默认值 |
| `{"type": "any"}` | 模型**必须**调用某个工具 | 需要保证结构化输出时 |
| `{"type": "tool", "name": "extract_metadata"}` | 模型**必须**调用特定工具 | 需要强制第一步/执行顺序时 |

**重要场景：**
- `tool_choice: "any"` + 多个提取工具 → 模型选择最佳工具，但仍能获得结构化输出
- 强制选择 → 需要保证特定首个操作（例如，在丰富之前执行 `extract_metadata`）

## 2.4 结构化输出的 JSON 模式

使用带 JSON 模式的 `tool_use` 是从 Claude 获取结构化输出的**最可靠**方式。它：
- 保证语法上有效的 JSON（无缺失括号，无尾随逗号）
- 强制执行所需结构（必填字段存在）
- **不**保证语义正确性（值仍可能是错误的）

**模式设计 — 关键原则：**

```json
{
  "type": "object",
  "properties": {
    "category": {
      "type": "string",
      "enum": ["bug", "feature", "docs", "unclear", "other"]
    },
    "category_detail": {
      "type": ["string", "null"],
      "description": "category = 'other' 或 'unclear' 时的详情"
    },
    "severity": {
      "type": "string",
      "enum": ["critical", "high", "medium", "low"]
    },
    "confidence": {
      "type": "number",
      "minimum": 0,
      "maximum": 1
    },
    "optional_field": {
      "type": ["string", "null"],
      "description": "如果在源中未找到信息则为 Null"
    }
  },
  "required": ["category", "severity"]
}
```

**模式设计规则：**
1. **必填与可选：** 仅当信息始终可用时才将字段标记为必填。必填字段会促使模型在数据缺失时捏造值。
2. **可空字段：** 对可能缺失的信息使用 `"type": ["string", "null"]`。模型可以返回 `null` 而非产生幻觉。
3. **含 `"other"` 的枚举：** 添加 `"other"` + 详情字符串，避免丢失预定义类别之外的数据。
4. **枚举 `"unclear"`：** 用于模型无法自信选择类别的情况——诚实的 `"unclear"` 优于错误的类别。

## 2.5 语法错误与语义错误

| 错误类型 | 示例 | 缓解措施 |
|---|---|---|
| **语法** | 无效 JSON，字段类型错误 | 使用 JSON 模式的 `tool_use`（可消除） |
| **语义** | 合计不符，值在错误字段中，幻觉 | 验证检查，带反馈的重试，自我纠正 |

---

# 第 3 章：Claude Agent SDK — 构建代理系统

> 文档：[Agent SDK](https://platform.claude.com/docs/en/agent-sdk/overview) | [Hooks](https://platform.claude.com/docs/en/agent-sdk/hooks) | [Subagents](https://platform.claude.com/docs/en/agent-sdk/subagents) | [Sessions](https://platform.claude.com/docs/en/agent-sdk/sessions)

## 3.1 什么是代理循环

代理循环是自主任务执行的核心模式。模型不只是回答——它执行一系列操作：

```
1. 向 Claude 发送带工具的请求
2. 接收响应
3. 检查 stop_reason：
   - "tool_use" -> 执行工具，将结果追加到历史，返回步骤 1
   - "end_turn" -> 任务完成，向用户显示结果
4. 重复直到完成
```

**这是模型驱动的方法：** Claude 根据上下文和先前的工具结果决定下一个要调用的工具。这与动作顺序固定的硬编码决策树不同。

**反模式（避免）：**
- 解析助手文本以检测完成（"任务已完成"）
- 使用任意迭代限制（例如 `max_iterations=5`）作为主要停止条件
- 检查助手是否产生文本内容作为完成信号

**正确方法：** 唯一可靠的完成信号是 `stop_reason == "end_turn"`。

## 3.2 `AgentDefinition` 配置

`AgentDefinition` 是 Claude Agent SDK 中的代理配置对象：

```python
agent = AgentDefinition(
    name="customer_support",
    description="处理客户的退货和订单问题",
    system_prompt="你是一个客户支持代理...",
    allowed_tools=["get_customer", "lookup_order", "process_refund", "escalate_to_human"],
    # 对于协调代理：
    # allowed_tools=["Task", "get_customer", ...]
)
```

**关键参数：**
- `name` / `description` — 代理的标识和描述
- `system_prompt` — 带指令的系统提示
- `allowed_tools` — 允许的工具列表（最小权限原则）

## 3.3 轮辐式：协调代理与子代理

多代理架构通常构建为轮辐式拓扑：

```
         协调代理
        /     |      \
   子代理1  子代理2  子代理3
   （搜索）  （分析）  （综合）
```

**协调代理负责：**
- 将任务分解为子任务
- 决定需要哪些子代理（动态选择）
- 将工作委派给子代理
- 聚合和验证结果
- 处理错误和重试
- 向用户传达结果

**关键原则：子代理有隔离的上下文。**
- 子代理**不会**自动继承协调代理的对话历史
- 所有必需的上下文必须在子代理提示中**显式传递**
- 子代理不在调用之间共享内存
- 所有通信通过协调代理流动（用于可观察性和错误控制）

## 3.4 用于生成子代理的 `Task` 工具

子代理通过 `Task` 工具生成：

```python
# 协调代理的 allowedTools 必须包含 "Task"
coordinator_agent = AgentDefinition(
    allowed_tools=["Task", "get_customer"]
)
```

**显式上下文传递是强制性的：**

```
# 不好：子代理没有上下文
Task: "分析文档"

# 好：提示中包含完整上下文
Task: "分析以下文档。
文档：[完整文档文本]
先前搜索结果：[网络搜索结果]
输出格式要求：[模式]"
```

**并行生成：** 协调代理可以在一个响应中调用多个 `Task`——子代理并行运行：

```
# 一个协调代理响应包含：
Task 1: "搜索关于 X 的文章"
Task 2: "分析文档 Y"
Task 3: "搜索关于 Z 的文章"
# 三个同时运行
```

## 3.5 Agent SDK 中的钩子

钩子允许在代理生命周期的特定点进行拦截和转换。

**PostToolUse** 在工具结果提供给模型之前拦截它：

```python
# 示例：规范化来自不同 MCP 工具的日期格式
@hook("PostToolUse")
def normalize_dates(tool_result):
    # 将 Unix 时间戳转换为 ISO 8601
    # 将 "Mar 5, 2025" 转换为 "2025-03-05"
    return normalized_result
```

**出站调用拦截钩子**阻止违反策略的操作：

```python
# 示例：阻止超过 500 美元的退款
@hook("PreToolUse")
def enforce_refund_limit(tool_call):
    if tool_call.name == "process_refund" and tool_call.args.amount > 500:
        return redirect_to_escalation(tool_call)
```

**关键区别：钩子与提示指令**

| 属性 | 钩子 | 提示指令 |
|---|---|---|
| 保证 | **确定性**（100%） | **概率性**（>90%，非 100%） |
| 使用时机 | 关键业务规则、财务操作、合规性 | 一般偏好、建议、格式 |
| 示例 | 阻止 > $500 的退款 | "尝试先解决再升级" |

**规则：** 当失败有财务、法律或安全后果时——使用钩子，而非提示。

## 3.6 `fork_session` 与会话管理

**`--resume <session-name>`** 恢复命名会话：

```bash
claude --resume investigation-auth-bug
```

- 继续之前保存上下文的对话
- 适用于跨多个会话的长期调查
- 风险：如果自上次会话以来文件已更改，工具结果可能已过时

**`fork_session`** 从共享上下文创建独立分支：

```
代码库调查
         |
    fork_session
    /           \
方法 A：         方法 B：
Redux           Context API
```

- 两个分支继承分支点之前的上下文
- 之后，它们独立分叉
- 适用于比较方法或测试策略

**何时启动新会话而非恢复：**
- 工具结果已过时（文件已更改）
- 已过很长时间，上下文已降级
- 以"以下是我们发现的简短摘要：..."重新开始，比用旧工具数据恢复更可靠

---

# 第 4 章：模型上下文协议（MCP）

> 文档：[MCP](https://modelcontextprotocol.io/) | [工具](https://modelcontextprotocol.io/docs/concepts/tools) | [资源](https://modelcontextprotocol.io/docs/concepts/resources) | [服务器](https://modelcontextprotocol.io/docs/concepts/servers)

## 4.1 什么是 MCP

模型上下文协议（MCP）是一种用于将外部系统连接到 Claude 的开放协议。MCP 定义了三种主要资源类型：

1. **工具** — 代理可以调用以执行操作的函数（CRUD 操作、API 调用、命令执行）
2. **资源** — 代理可以读取以获取上下文的数据（文档、数据库模式、内容目录）
3. **提示** — 用于常见任务的预定义提示模板

## 4.2 MCP 服务器

MCP 服务器是实现 MCP 协议并提供工具/资源的进程。当您连接到 MCP 服务器时：
- 所有工具都会自动被发现
- 来自所有已连接服务器的工具同时可用
- 工具描述决定模型将如何使用它们

## 4.3 配置 MCP 服务器

**项目配置（`.mcp.json`）** — 供团队使用：

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_TOKEN": "${GITHUB_TOKEN}"
      }
    },
    "jira": {
      "command": "npx",
      "args": ["-y", "mcp-server-jira"],
      "env": {
        "JIRA_TOKEN": "${JIRA_TOKEN}"
      }
    }
  }
}
```

**要点：**
- `.mcp.json` 存储在项目根目录并通过版本控制进行管理
- 环境变量（`${GITHUB_TOKEN}`）用于存储密钥——令牌本身不会被提交
- 所有项目贡献者均可使用

**用户配置（`~/.claude.json`）** — 用于个人/实验性服务器：
- 存储在用户的主目录中
- 不通过版本控制共享
- 适合个人实验和测试

**选择服务器：**
- 对于标准集成（Jira、GitHub、Slack），优先使用现有的社区 MCP 服务器
- 仅为独特的、团队专属的工作流构建自己的服务器

## 4.4 MCP 中的 `isError` 标志

当 MCP 工具遇到错误时，它在响应中使用 `isError: true`。这向代理发出信号，表明调用失败。

**结构化错误（推荐做法）：**

```json
{
  "isError": true,
  "content": {
    "errorCategory": "transient",
    "isRetryable": true,
    "message": "The service is temporarily unavailable. Timeout while calling the orders API.",
    "attempted_query": "order_id=12345",
    "partial_results": null
  }
}
```

**通用错误（反模式）：**

```json
{
  "isError": true,
  "content": "Operation failed"
}
```

通用错误不为代理提供任何决策信息——它应该重试、更改查询还是升级？

## 4.5 MCP 资源

资源是代理可以请求以获取上下文而无需执行操作的数据：

- 内容目录（例如，所有项目任务的列表、层级导航）
- 数据库模式（了解数据结构）
- 文档（API 参考、内部指南）
- 问题/任务摘要

**资源优势：** 代理无需进行探索性工具调用即可了解存在哪些数据。资源提供了一个即时的"地图"。

---

# 第 5 章：Claude Code — 配置与工作流

> 文档：[Claude Code](https://code.claude.com/docs/en/overview) | [内存 / CLAUDE.md](https://code.claude.com/docs/en/memory) | [技能](https://code.claude.com/docs/en/skills) | [MCP](https://code.claude.com/docs/en/mcp) | [钩子](https://code.claude.com/docs/en/hooks) | [子代理](https://code.claude.com/docs/en/sub-agents) | [GitHub Actions](https://code.claude.com/docs/en/github-actions) | [无头模式](https://code.claude.com/docs/en/headless)

## 5.1 CLAUDE.md 层级结构

CLAUDE.md 是 Claude Code 的指令文件。它有三个层级：

```
1. 用户级：~/.claude/CLAUDE.md
   - 仅适用于该用户
   - 不通过版本控制共享
   - 个人偏好和工作风格

2. 项目级：.claude/CLAUDE.md 或根目录 CLAUDE.md
   - 适用于所有项目贡献者
   - 通过版本控制管理
   - 编码标准、测试标准、架构决策

3. 目录级：子目录中的 CLAUDE.md
   - 在处理该目录中的文件时适用
   - 特定于代码库该部分的约定
```

**常见错误：** 新团队成员未能收到项目指令，因为这些指令被放在了 `~/.claude/CLAUDE.md`（用户级）而非 `.claude/CLAUDE.md`（项目级）。

## 5.2 `@path` 语法（文件导入）

CLAUDE.md 可以使用 `@path` 引用外部文件，使配置模块化：

```markdown
# 项目 CLAUDE.md

编码标准详见 @./standards/coding-style.md
测试要求详见 @./standards/testing-requirements.md
项目概述详见 @README.md，依赖项详见 @package.json
```

**`@path` 规则：**
- 在文件路径前紧跟 `@`（无空格）
- 支持相对路径和绝对路径
- 相对路径相对于包含导入的文件进行解析
- 最大导入嵌套深度为 5

这避免了重复，并使每个包只包含相关标准。

## 5.3 `.claude/rules/` 目录

`.claude/rules/` 是整体式 CLAUDE.md 的替代方案，用于按主题组织规则：

```
.claude/rules/
  testing.md          -- 测试约定
  api-conventions.md  -- API 约定
  deployment.md       -- 部署规则
  react-patterns.md   -- React 模式
```

**关键特性：带 `paths` 的 YAML 前置元数据用于条件加载：**

```yaml
---
paths: ["src/api/**/*"]
---

对于 API 文件，使用带有显式错误处理的 async/await。
每个端点必须返回标准响应包装器。
```

```yaml
---
paths: ["**/*.test.tsx", "**/*.test.ts"]
---

测试必须使用 describe/it 块。
使用数据工厂而非硬编码。
不要模拟数据库——使用测试数据库。
```

**工作原理：**
- 规则**仅**在 Claude Code 编辑与 `paths` 模式匹配的文件时加载
- 这节省了上下文和令牌——不相关的规则不会被加载
- Glob 模式让您可以按文件类型应用约定，而与位置无关（非常适合分散在整个代码库中的测试）

**何时使用带 `paths` 的 `.claude/rules/` 与目录级 CLAUDE.md：**
- 带 `paths` 的 `.claude/rules/` — 当约定适用于分散在多个目录中的文件时（测试、迁移）
- 目录级 CLAUDE.md — 当约定与特定目录绑定且在其他地方不需要时

## 5.4 自定义斜杠命令与技能

> **注意：** 在当前 Claude Code 版本中，自定义命令（`.claude/commands/`）与技能（`.claude/skills/`）已统一。两种格式都会创建 `/名称` 命令。考试指南引用了 `.claude/commands/` — 该格式仍受支持。

斜杠命令是通过 `/名称` 调用的可复用提示模板：

**`.claude/commands/` 格式（旧版，仍受支持）：**

```
.claude/commands/
  review.md        -- /review -- 标准代码审查
  test-gen.md      -- /test-gen -- 测试生成
```

**`.claude/skills/` 格式（当前）：**

```
.claude/skills/
  review/SKILL.md  -- /review -- 带前置元数据配置
  test-gen/SKILL.md
```

**项目命令**（`.claude/commands/` 或 `.claude/skills/`）：
- 存储在版本控制中，克隆仓库时对所有人可用
- 确保团队内工作流的一致性

**用户命令**（`~/.claude/commands/` 或 `~/.claude/skills/`）：
- 不通过版本控制共享的个人命令
- 用于个人工作流

## 5.5 技能 — `.claude/skills/`

技能是通过 SKILL.md 前置元数据配置的高级命令：

```yaml
---
context: fork
allowed-tools: ["Read", "Grep", "Glob"]
argument-hint: "要分析的目录路径"
---

分析指定目录中的代码结构。
输出关于依赖关系和架构模式的报告。
```

**前置元数据参数：**

| 参数 | 说明 |
|---|---|
| `context: fork` | 在隔离的子代理中运行技能。详细输出不会污染主会话 |
| `allowed-tools` | 限制可用的工具（安全性——例如，如果未被允许，技能无法删除文件） |
| `argument-hint` | 在不带参数调用时提示输入参数的提示语 |

**何时使用技能与 CLAUDE.md：**
- **技能** — 按需调用以完成特定任务（审查、分析、生成）
- **CLAUDE.md** — 始终加载的通用标准和约定

**个人技能（`~/.claude/skills/`）：**
- 以不同名称创建个人变体，不影响队友

## 5.6 规划模式与直接执行

**规划模式：**
- 模型仅进行调查和规划；不进行更改
- 使用 Read、Grep、Glob 探索代码库
- 生成供用户审批的实施计划
- 安全探索，无副作用

**何时使用规划模式：**
- 大规模更改（数十个文件）
- 存在多种可行方案（微服务：如何定义边界？）
- 架构决策（选择哪个框架？什么结构？）
- 不熟悉的代码库（更改前必须先理解）
- 影响 45 个以上文件的库迁移

**何时使用直接执行：**
- 有明确堆栈跟踪的单文件修复
- 添加一个验证检查
- 已充分理解、无歧义的更改

**组合方法：**
1. 使用规划模式进行调查和设计
2. 用户审批计划
3. 使用直接执行实施已审批的计划

**探索子代理** — 用于探索代码库的专用子代理：
- 将详细输出与主上下文隔离
- 仅返回摘要
- 防止多阶段任务中上下文窗口耗尽

## 5.7 `/compact` 命令

`/compact` 是用于压缩上下文的内置命令：
- 汇总先前的历史记录以释放上下文窗口
- 用于上下文被大量工具输出填满的长时间调查会话
- 风险：精确的数值、日期和具体细节可能在汇总过程中丢失

## 5.8 `/memory` 命令

`/memory` 是用于管理会话间内存的内置命令：
- 打开 `CLAUDE.md` 文件进行编辑，允许您保存笔记、偏好设置和上下文
- 信息在会话间持久保存，并在启动时自动加载
- 适用于存储项目约定、用户偏好、常用命令和当前工作上下文
- 无需在每个会话中重复说明相同指令的替代方案

## 5.9 用于 CI/CD 的 Claude Code CLI

**`-p`（或 `--print`）标志：**

```bash
claude -p "Analyze this pull request for security issues"
```

- 非交互式模式：处理提示，打印到标准输出，然后退出
- 不等待用户输入
- 在 CI/CD 管道中运行 Claude 的唯一正确方式

**用于 CI 的结构化输出：**

```bash
claude -p "Review this PR" --output-format json --json-schema '{"type":"object",...}'
```

- `--output-format json` — 以 JSON 格式输出
- `--json-schema` — 根据模式验证输出
- 结果可被解析以自动发布内联 PR 评论

**会话上下文隔离：**
生成代码的同一 Claude 会话在审查该代码时通常效果较差（模型保留了其推理上下文，不太可能质疑自己的决策）。使用独立实例进行审查。

**防止重复评论：**
在新提交后重新审查时，将之前的审查结果包含在上下文中，并指示 Claude 仅报告新问题或未解决的问题。

# 第6章：提示工程——高级技巧

> 文档：[提示工程](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview) | [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook)

## 6.1 少样本提示

少样本提示是在提示中包含2–4个输入/输出示例，以演示预期行为。

**为什么少样本比文字描述更有效：**
- "更精确"之类的模糊指令可以有多种解读方式
- 示例能明确展示预期格式和决策逻辑
- 模型将模式泛化到新情况（而不仅仅是重复示例）

**少样本示例的类型及使用时机：**

1. **针对模糊场景的示例：**

```
请求："我的订单坏了"
动作：调用 get_customer -> lookup_order -> check status。
理由："坏了"可能指商品损坏；需要订单详情。

请求："帮我找个经理"
动作：立即调用 escalate_to_human。
理由：客户明确要求人工服务。不要尝试自主解决。
```

2. **针对输出格式的示例：**

```
发现示例：
{
  "location": "src/auth/login.ts:42",
  "issue": "用户名参数中存在SQL注入",
  "severity": "critical",
  "suggested_fix": "使用参数化查询"
}
```

3. **区分可接受代码与问题代码的示例：**

```
// 可接受（不标记）：
const items = data.filter(x => x.active);

// 问题（标记）：
const items = data.filter(x => x.active == true); // 使用严格相等 ===
```

4. **从不同文档格式中提取的示例：**

```
带内联引用的文档：
"如研究所示（Smith, 2023），比率为42%。"
-> {"value": "42%", "source": "Smith, 2023", "type": "inline_citation"}

带参考书目引用的文档：
"比率为42%。[1]"
-> {"value": "42%", "source": "reference_1", "type": "bibliography"}
```

5. **非正式计量的示例：**

```
文本："大约两把米"
-> {"amount": "~100g", "original_text": "两把", "precision": "approximate"}

文本："一撮盐"
-> {"amount": "~1g", "original_text": "一撮", "precision": "approximate"}
```

少样本对于提取非正式和非标准计量单位尤其有效，因为这些单位种类繁多，纯粹基于规则的指令难以覆盖。

**提示中的格式规范化规则：**
当使用严格的JSON模式进行结构化输出时，在提示中添加规范化规则：

```
规范化：
- 日期：始终使用ISO 8601（YYYY-MM-DD）；"昨天" -> 计算绝对日期
- 货币：数字金额+货币代码；"五块钱" -> {"amount": 5, "currency": "CNY"}
- 百分比：小数形式；"一半" -> 0.5
```

这可以防止JSON语法有效但值不一致的语义错误。

## 6.2 明确标准与模糊指令

**差（模糊）：**

```
检查代码注释的准确性。
保守一点——只报告高置信度的发现。
```

**好（明确标准）：**

```
仅在以下情况下将注释标记为有问题：
1. 注释描述的行为与实际代码行为相矛盾
2. 注释引用了不存在的函数或变量
3. TODO/FIXME注释所指的bug已在代码中修复

不要标记：
- 仅在风格上过时的注释
- 措辞轻微不准确的注释
- 缺失的注释（这是单独的类别）
```

**用示例定义严重性标准：**

```
严重：用户运行时失败
  示例：处理付款时出现NullPointerException

高：安全漏洞
  示例：SQL注入、XSS、缺少授权检查

中：无即时影响的逻辑bug
  示例：排序错误、差一错误

低：代码质量
  示例：重复代码、小数据量的次优算法
```

## 6.3 提示链

提示链将复杂任务分解为一系列聚焦的步骤：

```
步骤1：分析 auth.ts（仅本地问题）
       -> 输出：auth.ts中的问题列表

步骤2：分析 database.ts（仅本地问题）
       -> 输出：database.ts中的问题列表

步骤3：集成检查（跨文件依赖）
       -> 输出：模块边界处的问题
```

**为什么重要：**
- 避免**注意力稀释**——当模型同时接收太多文件时，可能会遗漏某些文件中的bug，同时对其他文件只进行浅层评论
- 确保每个文件的分析质量一致
- 允许单独分析跨文件交互

**何时使用提示链与动态分解：**
- **提示链** — 可预测、可重复的任务（代码审查、文件迁移）
- **动态分解** — 开放式调查，子任务在执行过程中才变得清晰

## 6.4 "访谈"模式

在实施解决方案之前，Claude提出澄清问题：

```
Claude："在为API实现缓存之前，有几个问题：
1. 您偏好哪种缓存失效策略——TTL还是基于事件？
2. 当缓存不可用时，过时数据是否可以接受？
3. 缓存应该是按用户还是全局的？
4. 预期缓存的数据量是多少？"
```

**何时有用：**
- 陌生领域（金融科技、医疗、法律系统）
- 有非显而易见影响的任务（缓存策略、故障模式）
- 存在多种可行方案，最佳选择取决于上下文

## 6.5 验证与带反馈的重试

当提取的数据验证失败时：

```
步骤1：从文档中提取数据
步骤2：验证（Pydantic、JSON Schema、业务规则）
步骤3：如果有错误——带上下文重试：
  - 原始文档
  - 之前（错误的）提取结果
  - 具体错误："字段'total' = 150，但 sum(line_items) = 145。请重新检查值。"
```

**重试有效的情况：**
- 格式错误（日期格式不正确）
- 结构错误（字段放置位置错误）
- 算术不一致（模型可以重新检查）

**重试无效的情况：**
- 源文档中不存在该信息
- 所需上下文是外部的（数据在另一个未提供的文档中）

**Pydantic作为验证工具：**
Pydantic是一个用于基于模式的数据验证的Python库。对于考试，关键点是：
- **结构验证：** 在从Claude接收JSON后，在代码中检查类型、必填项、枚举约束
- **语义验证：** 自定义验证器强制执行业务逻辑（条目总和等于合计；start_date < end_date）
- **验证-重试循环：** 在Pydantic验证失败时，构建错误消息并带错误上下文重新提示Claude
- **JSON Schema生成：** Pydantic模型可以为`tool_use`生成JSON Schema，提供单一事实来源

## 6.6 自我纠正

检测内部矛盾的模式：

```json
{
  "stated_total": "$150.00",
  "calculated_total": "$145.00",
  "conflict_detected": true,
  "line_items": [
    {"name": "Widget A", "price": 75.00},
    {"name": "Widget B", "price": 70.00}
  ]
}
```

模型同时提取声明值和计算值——如果两者不同，`conflict_detected`允许您处理差异。

---

# 第7章：消息批处理API

> 文档：[消息批处理](https://platform.claude.com/docs/en/build-with-claude/message-batches)

## 7.1 概述

消息批处理API允许您提交批量请求进行异步处理：

| 属性 | 值 |
|---|---|
| 节省 | 与同步调用相比节省**50%** |
| 处理窗口 | 最长**24小时**（无延迟SLA保证） |
| 多轮工具调用 | **不支持**（一个请求=一个响应） |
| 关联 | `custom_id`字段用于关联请求和响应 |

## 7.2 何时使用批处理API与同步API

| 任务 | API | 原因 |
|---|---|---|
| 合并前PR检查 | **同步** | 开发者在等待；24小时不可接受 |
| 隔夜技术债务报告 | **批处理** | 早上需要结果；节省50% |
| 每周安全审计 | **批处理** | 不紧急；节省50% |
| 交互式代码审查 | **同步** | 需要立即响应 |
| 处理10,000个文档 | **批处理** | 批量处理；节省显著 |

## 7.3 使用 `custom_id`

```json
{
  "custom_id": "doc-invoice-2024-001",
  "params": {
    "model": "claude-sonnet-4-6",
    "max_tokens": 1024,
    "messages": [{"role": "user", "content": "从以下内容提取数据：..."}]
  }
}
```

`custom_id` 允许您：
- 将结果关联到原始文档
- 在失败时，仅重新提交失败的文档
- 避免重新处理成功的文档

## 7.4 处理批处理中的失败

1. 提交100个文档的批次
2. 95个成功；5个失败（超出上下文限制）
3. 通过`custom_id`识别失败项
4. 修改策略（例如，将长文档分割成块）
5. 仅重新提交5个失败的文档

## 7.5 SLA规划

如果您需要在30小时内得到结果，而批处理API最长需要24小时：
- 提交窗口：30 - 24 = **6小时**
- 批次必须在截止时间前至少24小时提交
- 对于频繁提交，分割为4小时窗口

---

# 第8章：任务分解策略

## 8.1 固定管道（提示链）

每个步骤都预先定义：

```
文档 -> 元数据提取 -> 数据提取 -> 验证 -> 富化 -> 最终输出
```

**何时使用：**
- 任务结构可预测（评审始终遵循相同模板）
- 所有步骤预先已知
- 需要稳定性和可重复性

## 8.2 动态自适应分解

子任务根据中间结果生成：

```
1. "为遗留代码库添加测试"
2. -> 首先：映射结构（Glob、Grep）
3. -> 发现：3个模块无测试，2个覆盖率不完整
4. -> 优先级：从支付模块开始（高风险）
5. -> 工作中：发现依赖外部API
6. -> 适应：在编写测试前为外部API添加mock
```

**何时使用：**
- 开放式调查任务
- 全部范围事先未知
- 每个步骤依赖前一步骤的结果

## 8.3 多轮代码审查

对于包含10个以上文件的拉取请求：

```
第1轮（逐文件）：分析 auth.ts -> 列出本地问题
第1轮（逐文件）：分析 database.ts -> 列出本地问题
第1轮（逐文件）：分析 routes.ts -> 列出本地问题
...
第2轮（集成）：分析文件间关系
  -> 跨文件问题：类型不一致、循环依赖
```

**为什么对14个文件进行单轮分析效果差：**
- 注意力稀释：对某些文件深度分析，对其他文件浅层分析
- 评论不一致：某个模式在一个文件中被标记，在另一个文件中被批准
- 遗漏bug：由于认知过载，明显错误被跳过

---

# 第9章：升级与人工参与

## 9.1 何时升级到人工

**升级触发条件（明确规则）：**

| 情况 | 动作 |
|---|---|
| 客户明确要求"帮我找个经理" | 立即升级；不要尝试解决 |
| 政策未涵盖该请求 | 升级（例如，政策未规定竞争对手价格匹配） |
| 代理无法取得进展 | 在合理次数尝试后升级 |
| 财务操作超过阈值 | 升级（最好通过钩子而非提示强制执行） |
| 搜索客户时出现多个匹配 | 请求额外标识符；不要猜测 |

**不可靠的触发条件：**

| 不可靠方法 | 失败原因 |
|---|---|
| 情感分析 | 客户情绪与案例复杂度不相关 |
| 模型自评置信度（1–10） | 模型可能自信地犯错；校准效果差 |
| 自动分类器 | 过度工程化；可能需要您没有的训练数据 |

## 9.2 升级模式

**立即升级：**

```
客户："我想和经理谈"
代理：[立即调用 escalate_to_human]
不应该："我可以帮您解决问题，让我..."
```

**尝试解决后升级：**

```
客户："我的冰箱购买两天后坏了"
代理：[检查订单，提供保修更换]
如果客户不满意 -> 升级
```

**细致的升级（承认 → 解决 → 重申时升级）：**

```
客户："太过分了，我对质量非常不满意！"
代理：[承认不满] "我理解您的不满。"
       [提供解决方案] "我可以提供更换或退款。"
客户："不，我要和人说话！"
代理：[客户再次坚持 -> 立即升级]
```

关键原则：先承认情绪，然后提出具体解决方案，只有当客户再次表达想要人工服务时才升级。不要在第一次表达不满时就升级（这与请求经理不同）。

**因政策缺口升级：**

```
客户："竞争对手X的这件商品便宜30%——给我打折"
政策：仅涵盖本网站的价格调整
代理：[升级——政策未涵盖竞争对手价格匹配]
```

## 9.3 结构化交接协议

升级时，代理应向人工传递结构化摘要：

```json
{
  "customer_id": "CUST-12345",
  "customer_name": "张三",
  "issue_summary": "损坏商品的退款请求",
  "order_id": "ORD-67890",
  "root_cause": "商品到货时损坏；已附照片",
  "actions_taken": [
    "通过 get_customer 验证客户",
    "通过 lookup_order 确认订单",
    "提供标准更换——客户坚持要求退款"
  ],
  "refund_amount": "$89.99",
  "recommended_action": "批准全额退款",
  "escalation_reason": "客户要求与经理交谈"
}
```

人工操作员无法访问完整的对话记录——他们只看到这份摘要。因此摘要必须完整且自包含。

## 9.4 置信度校准与人工监督

对于数据提取系统：

1. **字段级置信度评分：** 模型为每个提取字段输出置信度评分
2. **校准：** 使用标记的验证集来调整阈值
3. **路由：**
   - 高置信度+稳定准确率 -> 自动处理
   - 低置信度或来源模糊 -> 人工审查

**分层随机抽样：**
- 即使对于高置信度提取，也要定期审计样本
- 整体97%的准确率可能掩盖某种文档类型40%的错误
- 按文档类型和字段分析准确率，而不仅仅是整体分析

---

# 第10章：多代理系统中的错误处理

## 10.1 错误类别

| 类别 | 示例 | 可重试 | 代理动作 |
|---|---|---|---|
| **瞬态** | 超时、503、网络故障 | 是 | 使用指数退避重试 |
| **验证** | 输入格式无效、缺少必填字段 | 否（修复输入） | 修改请求后重试 |
| **业务** | 违反政策、超过阈值 | 否 | 向用户解释；提出替代方案 |
| **权限** | 拒绝访问 | 否 | 升级 |

## 10.2 错误处理反模式

| 反模式 | 问题 | 正确方法 |
|---|---|---|
| 通用状态"搜索不可用" | 协调代理无法决定如何恢复 | 返回错误类型、查询、部分结果、替代方案 |
| 静默抑制（空结果=成功） | 协调代理认为没有匹配，但实际是失败 | 区分"无结果"与"搜索失败" |
| 单个失败时中止整个工作流 | 丢失所有部分结果 | 继续使用部分结果；注释缺口 |
| 子代理内无限重试 | 延迟和资源浪费 | 本地恢复（1–2次重试），然后传递给协调代理 |

## 10.3 结构化子代理错误

```json
{
  "status": "partial_failure",
  "failure_type": "timeout",
  "attempted_query": "AI对音乐行业的影响2024",
  "partial_results": [
    {"title": "AI音乐生成报告", "url": "...", "relevance": 0.8}
  ],
  "alternative_approaches": [
    "尝试更窄的查询：'AI音乐创作工具'",
    "使用替代数据源"
  ],
  "coverage_impact": "未覆盖：AI对音乐制作的影响"
}
```

这为协调代理提供了决策所需的信息：
- 用修改后的查询重试？
- 使用部分结果？
- 委托给不同的子代理？
- 继续而不包含此部分并注释缺口？

## 10.4 最终综合中的覆盖注释

```markdown
## 报告：AI对创意产业的影响

### 视觉艺术（完整覆盖）
[研究结果]

### 音乐（部分覆盖——搜索代理超时）
[部分结果]
⚠️ 注意：由于搜索代理超时，本节覆盖范围有限。

### 文学（完整覆盖）
[研究结果]
```
