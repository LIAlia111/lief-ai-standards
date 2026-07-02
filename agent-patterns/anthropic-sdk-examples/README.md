# Anthropic Claude Agent SDK — 官方示例

> 来源：[anthropics/claude-agent-sdk-python](https://github.com/anthropics/claude-agent-sdk-python/tree/main/examples)  
> 整合日期：2026-07-03

## 文件说明

| 文件 | 说明 |
|---|---|
| `quick_start.py` | 最简入门：单次 query |
| `agents.py` | 自定义 Agent 定义与使用 |
| `hooks.py` | PreToolUse/PostToolUse/Stop 等 hook 模式 |
| `tools_option.py` | 工具权限控制（allowed_tools/disallowed_tools）|
| `system_prompt.py` | 自定义 system prompt |
| `plugin_example.py` | 加载本地 plugin |

## 核心用法

```python
from claude_agent_sdk import query, ClaudeAgentOptions

options = ClaudeAgentOptions(
    system_prompt="...",
    allowed_tools=["Read", "Write", "Bash"],
    permission_mode="acceptEdits"
)

async for message in query(prompt="任务描述", options=options):
    print(message)
```

## 安装

```bash
pip install claude-agent-sdk
```
