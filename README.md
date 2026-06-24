# Agent Team Selector

`agent-team-selector` 是一个 Codex Skill，用来在项目开始前分析你的需求，并从 subagent/agent 角色库里推荐最小但足够强的协作组合。

它的目标是让项目执行更高效、更准确，并通过合适的测试、审查和风险角色降低 BUG 率。

## 适合什么场景

当你准备让 Codex 开始一个项目、功能、重构、调试、迁移、发布或代码审查时，可以先使用这个 skill 生成推荐 agent 团队。

典型请求：

```text
用 agent-team-selector 分析这个项目请求，推荐最优 subagent 组合：
我要做一个带登录、数据库、后台管理和部署流程的 SaaS MVP。
```

它会输出：

- 推荐的 agent 团队
- 每个 agent 的职责
- 为什么选择这些 agent
- 执行顺序
- 没有选择的关键 agent 及原因
- 可直接复制给 Codex 的协作提示词

## 核心设计

这个 skill 不负责直接实现项目，而是负责在项目启动前做 agent 编排建议。

默认原则：

- 小任务少开 agent，避免过度编排。
- 中等任务保留 `planner`、`coder`、`tester`、`reviewer`。
- 复杂任务按风险补充 `architect`、`security`、`database`、`performance`、`devops` 等专家角色。
- 始终优先选择能明显降低错误率或提升交付质量的 agent。

## 目录结构

```text
agent-team-selector/
├─ SKILL.md
├─ agents/
│  └─ openai.yaml
└─ references/
   ├─ subagent-library.md
   ├─ selection-rules.md
   └─ team-presets.md
```

### 文件说明

- `SKILL.md`：skill 主说明，定义触发场景、工作流、输出格式和约束。
- `references/subagent-library.md`：完整 subagent 角色库。
- `references/selection-rules.md`：选择规则，用来判断什么时候加入或排除某个 agent。
- `references/team-presets.md`：常见项目类型的 agent 组合模板。
- `agents/openai.yaml`：Codex UI 元数据。

## 安装

把整个目录复制到 Codex skills 目录：

```powershell
Copy-Item -Recurse .\agent-team-selector C:\Users\<你的用户名>\.codex\skills\agent-team-selector
```

然后重启 Codex 或新开一个会话。

## 使用示例

### 全栈项目

```text
用 agent-team-selector 分析这个项目请求，推荐最优 subagent 组合：
我要做一个全栈任务管理系统，包含登录、团队协作、数据库、API、前端界面和部署。
```

可能推荐：

```text
product / architect / frontend / backend / database / tester / security / reviewer
```

### Bug 修复

```text
用 agent-team-selector 分析这个项目请求：
现有项目登录后偶尔跳回登录页，需要定位并修复。
```

可能推荐：

```text
debugger / auth / coder / tester / reviewer
```

### 性能问题

```text
用 agent-team-selector 分析这个项目请求：
后台报表页面加载很慢，数据库查询和前端渲染都可能有问题。
```

可能推荐：

```text
debugger / performance / database / frontend / tester / reviewer
```

## 常见 Agent 类型

核心通用：

```text
main / planner / architect / coder / tester / reviewer
```

发现与分析：

```text
researcher / codebase-explorer / requirements-analyst / debugger / log-analyst
```

产品与设计：

```text
product / ux-designer / ui-designer / accessibility / content-designer
```

前端：

```text
frontend / react-specialist / vue-specialist / mobile-ui / browser-tester
```

后端：

```text
backend / api-designer / database / auth / integration
```

质量与风险：

```text
qa / security / performance / reliability / observability
```

基础设施：

```text
devops / cloud / container / release-manager / repo-maintainer
```

文档与沟通：

```text
docs / technical-writer / changelog / support
```

专项：

```text
data-engineer / ml-engineer / analytics / migration / localization / legal-compliance
```

## 注意事项

这个 skill 推荐的是“最优 agent 组合”。是否能真正启动多个 subagent，取决于当前 Codex 环境是否暴露 subagent/multi-agent 工具。

如果环境没有真实 subagent 能力，这个 skill 仍然有用：Codex 可以按这些角色顺序分析和执行，相当于用结构化角色分工降低遗漏。
