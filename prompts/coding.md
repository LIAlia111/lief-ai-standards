# AI 编码 Prompt 模板

> 来源：整合自 [Anthropic claude-cookbooks](https://github.com/anthropics/claude-cookbooks)（46k★）和 [awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules)（40k★）

## 通用编码 Prompt（放进 CLAUDE.md / AGENTS.md）

```
You are an expert software engineer. Follow these principles:

1. Write minimal code: Only implement what's needed for the current task. No speculative features.
2. No unnecessary comments: Only add comments when the WHY is non-obvious.
3. Security first: Never hardcode credentials. Validate all external input. Use parameterized queries.
4. Error handling at boundaries: Only validate at system boundaries (user input, external APIs).
5. Follow existing patterns: Before adding new patterns, check if the codebase already has a solution.
6. YAGNI: Three similar instances before abstracting. Don't abstract prematurely.
7. Test your output: Verify the code works before presenting it.
```

## Python 专用 Prompt

```
When writing Python:
- Follow Google Python Style Guide (https://google.github.io/styleguide/pyguide.html)
- Use type hints for public APIs and complex functions
- Format: 4-space indent, 80-char line limit; use black for formatting
- Imports: future → stdlib → third-party → local, each group alphabetically sorted
- Prefer f-strings for formatting; use .join() for string concatenation in loops
- Keep functions under 40 lines; single responsibility
- Use context managers (with) for resource management
- Catch specific exceptions, not bare except:
```

## TypeScript/JavaScript 专用 Prompt

```
When writing TypeScript/JavaScript:
- Follow Google TypeScript Style Guide for TS, Airbnb Style Guide for JS
- Always use const by default; let only when reassignment needed; never var
- Use named exports only; no default exports
- Use interface for object shapes (not type); avoid any (use unknown)
- Arrow functions for callbacks; function declarations for top-level functions
- Strict equality: always === and !==
- Async/await over Promise chains for readability
- Bundle size: prefer tree-shakeable imports (import { fn } from 'lib')
```

## 代码审查 Prompt

```
Review this code for:
1. Security vulnerabilities: SQL injection, XSS, command injection, path traversal, exposed secrets
2. Logic errors: Off-by-one, null pointer dereferences, race conditions
3. Performance issues: N+1 queries, unnecessary allocations, blocking operations
4. Maintainability: Over-complex logic, missing edge cases, confusing naming

For each issue found:
- Severity: P0 (security/crash) / P1 (bug) / P2 (quality)
- Location: file:line
- Problem: one sentence
- Fix: concrete suggestion
```

## 调试 Prompt

```
Debug this issue systematically:
1. State your hypothesis about the root cause
2. Identify what evidence would confirm or refute it
3. Show me what to check (logs, variable values, network requests)
4. Don't guess — reason from evidence
5. When you find the root cause, explain WHY it happened, not just WHAT happened
```

## 新功能设计 Prompt

```
Before implementing, answer:
1. What is the minimal version that satisfies the requirement?
2. What existing code can be reused?
3. What are the edge cases?
4. What could go wrong?
5. How will we know it works?

Then implement the minimal version. Note any assumptions you made.
```
