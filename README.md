# lief-ai-standards

> AI 编码标准完整参考库——直接整合 **Anthropic / Google / OpenAI / Airbnb / awesome-cursorrules** 官方内容，让 Claude Code / Cursor / Copilot 本地开发遵循业界最高标准。

**共 63 个文件 · 8 大目录 · 全部原文搬运自官方 GitHub 仓库**

## 仓库结构

```
lief-ai-standards/
│
├── AGENTS.md                          # AI Agent 跨工具行为规范（Codex/Cursor/Claude/Copilot 通用）
│
├── rules/                             # 7 种语言规范（提炼版·AI 直接可读）
│   ├── python.md                      # Google Python Style Guide 提炼
│   ├── javascript.md                  # Airbnb JavaScript Guide 提炼
│   ├── typescript.md                  # Google TypeScript Guide 提炼
│   ├── go.md                          # Google Go Style Guide 提炼
│   ├── java.md                        # Google Java Style Guide 提炼
│   ├── cpp.md                         # Google C++ Style Guide 提炼
│   └── shell.md                       # Google Shell Guide 提炼
│
├── google-styleguide/                 # Google 官方完整规范（原文·数十万字）
│   ├── python-full.md                 # Google pyguide.md 完整版（115KB）
│   ├── shell-full.md                  # Google shellguide.md 完整版（40KB）
│   ├── csharp.md                      # Google C# Style Guide
│   ├── go-best-practices.md           # Google Go 最佳实践（138KB）
│   ├── go-decisions.md                # Google Go 风格决策集（126KB）
│   ├── pylintrc                       # Google Python pylint 配置（可直接导入 CI）
│   └── doc-style.md                   # Google Markdown 文档风格规范
│
├── cursorrules/                       # awesome-cursorrules 官方规范（AI 行为约束 · 36 个文件）
│   ├── meta/                          # 通用 AI 行为约束（最高价值 · 4 个）
│   │   ├── anti-overengineering.mdc  # 防止 AI 过度工程化
│   │   ├── clean-code.mdc            # Clean Code 原则
│   │   ├── ai-agent-specialist.mdc   # AI Agent 专家规范
│   │   └── security-devsecops.mdc    # DevSecOps 安全规范
│   ├── python/                        # Python 栈（4 个）
│   ├── typescript/                    # TypeScript/前端栈（3 个）
│   ├── go/                            # Go 后端（1 个）
│   ├── testing/                       # 测试规范（2 个）
│   ├── react/                         # React 生态（7 个）⭐ 新增
│   │   ├── react.mdc                 # React 核心规范
│   │   ├── react-typescript-nodejs.mdc # React + TS + Node.js
│   │   ├── react-redux-typescript.mdc  # React + Redux + TS
│   │   ├── react-zustand.mdc          # React + Zustand 状态管理
│   │   ├── react-query.mdc            # React Query / TanStack Query
│   │   ├── react-native-expo.mdc      # React Native + Expo
│   │   └── react-components.mdc       # React 组件创建规范
│   ├── nextjs/                        # Next.js 生态（5 个）⭐ 新增
│   │   ├── nextjs.mdc                 # Next.js 核心规范
│   │   ├── nextjs-app-router.mdc      # App Router 最佳实践
│   │   ├── nextjs15-react19-vercelai.mdc # Next.js 15 + React 19 + Vercel AI
│   │   ├── nextjs-typescript.mdc      # Next.js + TypeScript
│   │   └── nextjs-supabase-shadcn.mdc # Next.js + Supabase + shadcn/ui
│   ├── flutter/                       # Flutter 生态（3 个）⭐ 新增
│   │   ├── flutter-app-expert.mdc     # Flutter App 专家规范
│   │   ├── flutter-riverpod.mdc       # Flutter + Riverpod 状态管理
│   │   └── flutter-guidelines.mdc     # Flutter 开发通用准则
│   ├── mobile/                        # 移动端（3 个）⭐ 新增
│   │   ├── android-jetpack-compose.mdc # Android Jetpack Compose
│   │   ├── swiftui-guidelines.mdc     # SwiftUI 开发指南
│   │   └── swift-uikit.mdc            # Swift + UIKit 规范
│   └── devops-git/                    # DevOps / Git 规范（4 个）⭐ 新增
│       ├── docker.mdc                 # Docker 容器化规范
│       ├── git-conventional-commits.mdc # Conventional Commits 规范
│       ├── gitflow.mdc                # Git Flow 工作流
│       └── github-code-quality.mdc    # GitHub 代码质量规范
│
├── agent-patterns/                    # AI Agent 设计模式（Anthropic + OpenAI 官方 · 10 个文件）
│   ├── claude-agent-sdk-readme.md    # Anthropic Claude Agent SDK 完整 README（8.8KB）⭐
│   ├── claude-agent-basic-workflows.md # Claude Agent 基础工作流 Notebook 内容⭐ 新增
│   ├── claude-orchestrator-workers.md  # Claude Orchestrator-Workers 模式⭐ 新增
│   ├── claude-evaluator-optimizer.md   # Claude Evaluator-Optimizer 模式⭐ 新增
│   ├── claude-agent-patterns-guide.md  # Claude Agent 模式使用指南
│   ├── claude-cookbooks-overview.md    # claude-cookbooks 全览
│   ├── openai-reliability-techniques.md # OpenAI 可靠性提升 6 大技巧（42KB）
│   ├── openai-how-to-work-with-llms.md  # OpenAI 大型语言模型使用方法⭐ 新增
│   └── openai-codex-exec-plans.md       # OpenAI Codex 执行计划⭐ 新增
│
└── prompts/
    └── coding.md                      # 编码 Prompt 模板
```

## 来源一览

| 目录 | 来源 | Stars | 内容量 |
|---|---|---|---|
| `rules/` | Google Styleguide + Airbnb | 36k★ / 148k★ | 7 种语言提炼版规范 |
| `google-styleguide/` | [google/styleguide](https://github.com/google/styleguide) | 36k★ | 完整原文（Python 115KB / Go 138KB）|
| `cursorrules/meta/` | [awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules) | 40k★ | 4 个 AI 行为约束规则 |
| `cursorrules/python-go-ts-testing/` | awesome-cursorrules | 40k★ | 10 个后端+测试规则 |
| `cursorrules/react/` | awesome-cursorrules | 40k★ | 7 个 React 生态规则 |
| `cursorrules/nextjs/` | awesome-cursorrules | 40k★ | 5 个 Next.js 生态规则 |
| `cursorrules/flutter/` | awesome-cursorrules | 40k★ | 3 个 Flutter 规则 |
| `cursorrules/mobile/` | awesome-cursorrules | 40k★ | 3 个 iOS/Android 规则 |
| `cursorrules/devops-git/` | awesome-cursorrules | 40k★ | 4 个 DevOps/Git 规则 |
| `agent-patterns/` | [claude-cookbooks](https://github.com/anthropics/claude-cookbooks) + [openai-cookbook](https://github.com/openai/openai-cookbook) | 46k★ / 74k★ | 10 个 Agent 设计模式文档 |

## 用法

### 1. 作为 Claude Code 的编码规范引用

在项目 `CLAUDE.md` 中指向此仓库：

```markdown
# 编码规范参考
- 语言规范：https://github.com/LIAlia111/lief-ai-standards/tree/main/rules
- AI 行为约束（最重要）：https://github.com/LIAlia111/lief-ai-standards/tree/main/cursorrules/meta
- Agent 设计模式：https://github.com/LIAlia111/lief-ai-standards/tree/main/agent-patterns
```

### 2. 把 cursorrules/meta/ 规则直接复制进项目

最高价值的 4 个文件——复制进 `.cursorrules` 或 `CLAUDE.md`：

- `cursorrules/meta/anti-overengineering.mdc` — 防止 AI 默认往大了写（**强烈推荐**）
- `cursorrules/meta/clean-code.mdc` — Clean Code 执行原则
- `cursorrules/meta/ai-agent-specialist.mdc` — AI Agent 开发专项规范
- `cursorrules/meta/security-devsecops.mdc` — 安全规范

### 3. 按技术栈选择 cursorrules

- **React 项目** → `cursorrules/react/react.mdc` + `react-typescript-nodejs.mdc`
- **Next.js 项目** → `cursorrules/nextjs/nextjs-app-router.mdc` + `nextjs15-react19-vercelai.mdc`
- **Flutter 项目** → `cursorrules/flutter/flutter-app-expert.mdc` + `flutter-riverpod.mdc`
- **Python 后端** → `cursorrules/python/best-practices.mdc` + `fastapi.mdc`
- **Git 规范** → `cursorrules/devops-git/git-conventional-commits.mdc`

### 4. 参考 agent-patterns/ 设计 AI Agent

- `claude-agent-basic-workflows.md` — 顺序、并行、路由、编排 4 种基础模式
- `claude-orchestrator-workers.md` — Orchestrator-Workers 模式（分发多 Agent）
- `openai-reliability-techniques.md` — 提升可靠性的 6 大 Prompt 技巧
- `openai-codex-exec-plans.md` — Codex 执行计划设计

### 5. 配置 Python lint 检查

```bash
# 直接使用 Google Python pylint 配置
cp google-styleguide/pylintrc .pylintrc
```

## 维护原则

- 内容全部来自官方仓库原文，不自行改写或二次创作
- 各文件顶部保留原始来源链接
- 定期从官方上游同步更新
