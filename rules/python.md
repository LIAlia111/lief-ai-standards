# Python 编码规范

## 版本与工具

- Python >= 3.10
- 格式化：`black`（行长 100）
- Lint：`ruff`
- 类型检查：`mypy`（strict 模式可选，新项目推荐开）

## 项目结构（标准）

```
project/
├── src/
│   └── mypackage/
│       ├── __init__.py
│       ├── models.py
│       ├── services.py
│       └── utils.py
├── tests/
│   └── test_services.py
├── pyproject.toml
└── README.md
```

## 类型注解

```python
# ✅ 好：函数有完整注解
def get_user(user_id: int) -> User | None:
    ...

# ❌ 差：没有注解
def get_user(user_id):
    ...
```

## Dataclass / Pydantic

```python
# 数据模型优先用 dataclass 或 Pydantic，不用裸 dict
from dataclasses import dataclass

@dataclass
class User:
    id: int
    name: str
    email: str
```

## 异步

- IO 密集用 `asyncio`，不用线程
- 函数签名 `async def`，调用处必须 `await`
- 不在 async 函数里调用同步阻塞 IO

## 包管理

- 新项目用 `uv`（2025 推荐），不用 pip+virtualenv
- 依赖写进 `pyproject.toml`，不用 requirements.txt

## 常用规范

```python
# 列表推导式（简单逻辑）
names = [u.name for u in users if u.active]

# 复杂逻辑用普通循环，不要强行压一行
result = []
for user in users:
    if user.active and user.role == "admin":
        result.append(transform(user))

# 上下文管理器处理资源
with open("file.txt", "r", encoding="utf-8") as f:
    content = f.read()
```
