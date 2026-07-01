# AGENTS.md

> 跨 AI 工具统一行为规范（Claude Code / Cursor / GitHub Copilot / Codex / Windsurf 通用）
> 基于 [AGENTS.md 社区标准](https://github.com/agentsmd/agents.md)（Linux Foundation · 22k★）

## 覆盖工具

| 工具 | 读取文件 | 优先级 |
|---|---|---|
| Claude Code | `CLAUDE.md` > `AGENTS.md` | 高 |
| Cursor | `.cursorrules` > `AGENTS.md` | 高 |
| GitHub Copilot | `.github/copilot-instructions.md` > `AGENTS.md` | 高 |
| OpenAI Codex | `AGENTS.md` | 原生 |
| Windsurf | `AGENTS.md` | 高 |

## 核心行为规范

### 代码质量
- 只写解决当前问题的最少代码，不加「以后可能会用」的功能（YAGNI）
- 三处相似代码才考虑抽象，不过早抽象
- 默认写不含注释的代码；只有 WHY 非显而易见时才加注释
- 不写描述 WHAT 的注释（代码本身已说明）

### 安全优先
- 不在代码中硬编码 API key、密码、token
- 所有外部输入必须验证（SQL 参数化、HTML 转义、路径过滤）
- 不引入不必要的外部依赖
- 敏感信息走环境变量，不走代码文件

### 错误处理
- 只在系统边界（用户输入、外部 API）处验证和处理错误
- 不为不可能发生的情况写 fallback
- 错误消息对终端用户安全（不泄漏内部路径/堆栈）

### 沟通规范
- 完成任务后简短说明做了什么和为什么
- 遇到模糊需求先澄清再动手，不带假设往前冲
- 发现副作用（波及其他文件/系统）主动告知

## 语言规范

各语言详细规范见 `rules/` 目录：
- `rules/python.md` — Google Python Style Guide
- `rules/javascript.md` — Airbnb JavaScript Style Guide
- `rules/typescript.md` — Google TypeScript Style Guide
- `rules/go.md` — Google Go Style Guide
- `rules/java.md` — Google Java Style Guide
- `rules/cpp.md` — Google C++ Style Guide
- `rules/shell.md` — Google Shell Style Guide

## 参考来源

- [agentsmd/agents.md](https://github.com/agentsmd/agents.md) — Linux Foundation 跨工具 AI 编程标准
- [awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules) — 40k★ 各语言 Cursor 规范集合
- [Anthropic claude-cookbooks](https://github.com/anthropics/claude-cookbooks) — 46k★ Anthropic 官方示例
