# lief-ai-standards

AI 辅助开发的编码规范库。让 Claude Code / Cursor / Copilot 写代码时有统一标准可依。

## 目录结构

```
├── AGENTS.md              # 跨工具通用 AI 编码规范
├── rules/
│   ├── general.md         # 通用编码规范
│   ├── python.md          # Python 项目规范
│   └── typescript.md      # TypeScript 项目规范
└── prompts/
    ├── coding.md          # 代码生成 prompt 模板
    └── review.md          # 代码审查 prompt 模板
```

## 用法

在你的项目 CLAUDE.md 里引用对应规范，Claude Code 每次 session 自动加载：

```markdown
# 引用 Python 规范
@https://raw.githubusercontent.com/LIAlia111/lief-ai-standards/main/rules/python.md

# 引用通用规范
@https://raw.githubusercontent.com/LIAlia111/lief-ai-standards/main/rules/general.md
```

## 参考来源

- [Anthropic claude-cookbooks](https://github.com/anthropics/claude-cookbooks) 46k★
- [PatrickJS/awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules) 40k★
- [agentsmd/agents.md](https://github.com/agentsmd/agents.md) 22k★
- [Claude Code Best Practices](https://code.claude.com/docs/en/best-practices)

