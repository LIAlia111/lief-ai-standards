# lief-ai-standards

> AI 编码标准完整参考库——直接整合 **Anthropic / Google / OpenAI / Airbnb / awesome-cursorrules** 官方内容，让 Claude Code / Cursor / Copilot 本地开发遵循业界最高标准。

## 仓库结构

```
lief-ai-standards/
├── AGENTS.md                          # AI Agent 跨工具行为规范（Codex/Cursor/Claude/Copilot 通用）
│
├── rules/                             # 各语言规范（提炼版·AI 直接可读）
│   ├── python.md                      # Google Python Style Guide 提炼版
│   ├── javascript.md                  # Airbnb JavaScript Style Guide 提炼版
│   ├── typescript.md                  # Google TypeScript Style Guide 提炼版
│   ├── go.md                          # Google Go Style Guide 提炼版
│   ├── java.md                        # Google Java Style Guide 提炼版
│   ├── cpp.md                         # Google C++ Style Guide 提炼版
│   └── shell.md                       # Google Shell Style Guide 提炼版
│
├── google-styleguide/                 # Google 官方完整规范（原文搬运·115KB+）
│   ├── python-full.md                 # Google pyguide.md 完整版（115KB）
│   ├── shell-full.md                  # Google shellguide.md 完整版（40KB）
│   ├── csharp.md                      # Google C# Style Guide 完整版
│   ├── go-best-practices.md           # Google Go 最佳实践完整版（138KB）
│   ├── go-decisions.md                # Google Go 风格决策集完整版（126KB）
│   ├── pylintrc                       # Google Python pylint 配置（可直接导入 CI）
│   └── doc-style.md                   # Google Markdown 文档风格规范
│
├── cursorrules/                       # awesome-cursorrules 官方规范（直接复用）
│   ├── meta/                          # 通用 AI 行为约束（最高价值）
│   │   ├── anti-overengineering.mdc  # 防止 AI 过度工程化
│   │   ├── clean-code.mdc            # Clean Code 原则
│   │   ├── ai-agent-specialist.mdc   # AI Agent 专家规范
│   │   └── security-devsecops.mdc    # DevSecOps 安全规范
│   ├── python/                        # Python 技术栈
│   │   ├── best-practices.mdc        # Python 最佳实践综合
│   │   ├── fastapi.mdc               # Python + FastAPI 生产规范
│   │   ├── llm-ml-workflow.mdc       # Python LLM/ML 工作流
│   │   └── containerization.mdc      # Python 容器化规范
│   ├── typescript/                    # TypeScript/前端技术栈
│   │   ├── convention.mdc            # TypeScript 代码规范约定
│   │   ├── nestjs.mdc                # TypeScript + NestJS 最佳实践
│   │   └── nextjs-tailwind.mdc       # Next.js + TypeScript + Tailwind
│   ├── go/
│   │   └── backend-scalability.mdc   # Go 后端可扩展规范
│   └── testing/
│       ├── playwright.mdc            # Playwright E2E 测试规范
│       └── jest.mdc                  # Jest 单元测试规范
│
├── agent-patterns/                    # AI Agent 设计模式（Anthropic + OpenAI 官方）
│   ├── claude-agent-sdk.md           # Anthropic Claude Agent SDK 文档
│   ├── claude-cookbooks-overview.md  # Anthropic claude-cookbooks 全览
│   └── openai-reliability-techniques.md  # OpenAI 可靠性提升 6 大技巧
│
└── prompts/
    └── coding.md                      # 编码 Prompt 模板（含代码审查/调试/设计）
```

## 来源一览

| 目录 | 来源 | Stars | 内容 |
|---|---|---|---|
| `rules/` | Google Styleguide + Airbnb | 36k★ / 148k★ | 7 种语言提炼版规范 |
| `google-styleguide/` | [google/styleguide](https://github.com/google/styleguide) | 36k★ | 完整原文（Python 115KB / Go 138KB） |
| `cursorrules/` | [awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules) | 40k★ | AI 行为约束规则（meta/Python/TS/Go/测试） |
| `agent-patterns/` | [claude-cookbooks](https://github.com/anthropics/claude-cookbooks) + [openai-cookbook](https://github.com/openai/openai-cookbook) | 46k★ / 74k★ | Agent 设计模式 |
| `prompts/` | Anthropic + awesome-cursorrules | - | AI 编码 Prompt 模板 |

## 用法

### 1. 在 CLAUDE.md 里引用

```markdown
# 编码规范
- 语言规范：https://github.com/LIAlia111/lief-ai-standards/tree/main/rules
- AI 行为约束：https://github.com/LIAlia111/lief-ai-standards/tree/main/cursorrules/meta
```

### 2. 把 cursorrules/meta/ 的规则复制进项目 .cursorrules 或 CLAUDE.md

`cursorrules/meta/anti-overengineering.mdc` — 防止 AI 默认往大了写
`cursorrules/meta/clean-code.mdc` — Clean Code 原则执行
`cursorrules/meta/ai-agent-specialist.mdc` — AI Agent 开发专项规范

### 3. 用 google-styleguide/pylintrc 配置 Python lint

```bash
cp google-styleguide/pylintrc .pylintrc
```

### 4. 参考 agent-patterns/ 设计 AI 工作流

`openai-reliability-techniques.md` — CoT / 分解 / 自检 6 大可靠性技巧

## 维护

内容直接来自官方仓库，不自行改写。各文件顶部保留原始来源链接。
