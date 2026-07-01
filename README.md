# lief-ai-standards

> AI 写代码的编码标准参考库——直接采用 **Google / Airbnb / Anthropic / OpenAI** 官方标准，让 Claude Code 本地开发遵循业界最高标准。

## 用法

在 `CLAUDE.md` 或 `AGENTS.md` 里引用本仓库的规范文件：

```markdown
参考编码规范：https://github.com/LIAlia111/lief-ai-standards/blob/main/rules/<language>.md
```

或者克隆本仓库，把 `rules/` 目录的规范文件放进你的项目根目录。

## 来源（全部官方）

| 语言 | 来源 | Stars |
|---|---|---|
| Python | [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html) | 36k+ |
| JavaScript | [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) | 148k★ |
| TypeScript | [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html) | 36k+ |
| Go | [Google Go Style Guide](https://google.github.io/styleguide/go/guide) | 36k+ |
| Java | [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html) | 36k+ |
| C++ | [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html) | 36k+ |
| Shell/Bash | [Google Shell Style Guide](https://google.github.io/styleguide/shellguide.html) | 36k+ |

## 结构

```
lief-ai-standards/
├── AGENTS.md          # AI Agent 跨工具标准（Linux Foundation AGENTS.md spec）
├── rules/
│   ├── python.md      # Google Python Style Guide 核心要点
│   ├── javascript.md  # Airbnb JavaScript Style Guide 核心要点
│   ├── typescript.md  # Google TypeScript Style Guide 核心要点
│   ├── go.md          # Google Go Style Guide 核心要点
│   ├── java.md        # Google Java Style Guide 核心要点
│   ├── cpp.md         # Google C++ Style Guide 核心要点
│   └── shell.md       # Google Shell Style Guide 核心要点
└── prompts/
    └── coding.md      # Anthropic 官方编码 Prompt 模板（含代码审查/调试/设计）
```

## 维护

规范来自官方源头，随官方更新时同步。每条规范保留原文出处 URL，不自行改写官方内容。
