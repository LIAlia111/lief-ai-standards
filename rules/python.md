# Python 编码规范

> 来源：[Google Python Style Guide](https://google.github.io/styleguide/pyguide.html)

## 命名规范

- 模块名、变量名用 `lower_with_under`；类名用 `CapWords`；常量用 `CAPS_WITH_UNDER`
- 内部/受保护成员加单下划线前缀 `_`；不用双下划线 `__` 做名称修饰
- 名称描述性与作用域可见性成正比；单字母仅用于计数器、异常变量或约定符号
- 包名/模块名不用破折号；文件名加 `.py` 扩展名
- 获取器/设置器命名为 `get_foo()` / `set_foo()`；简单属性访问用 `@property`

## 注释与 Docstring

- 模块顶部写模块级 docstring，说明内容和用途
- 公开 API、非平凡函数、非显而易见逻辑必须写 docstring
- 函数 docstring 结构：`Args` / `Returns` / `Raises` 各节，正确缩进
- 所有 docstring 用三双引号；摘要行不超过 80 字符
- TODO 注释格式：`# TODO: resource_link - 描述`；不带个人信息
- 注释只说明「为什么」或「做什么」，不描述显而易见的代码行为

## 类型注解

- 公开 API 和复杂/易出错代码加注解；并非每个函数都必须加
- 用 `X | None` 代替 `Optional[X]`；可空类型必须显式声明
- 有类型注解时，默认参数值的 `=` 两侧加空格
- 直接导入 typing 符号：`from typing import Any, Callable`
- 函数签名中用 `Sequence` 等抽象类型，不用具体 `list` 或 `tuple`
- 类型别名用 CapWords 命名，使用 `TypeAlias` 注解声明
- 用 `from __future__ import annotations` 处理前向声明和自引用类型

## 模块结构与导入

- 导入置于文件顶部，模块 docstring 之后，顺序：`future` → stdlib → 第三方 → 本地
- 用完整包路径 `from package.module import name`，不用相对导入
- 各组内按字母序排列；组间空一行
- 每行一条语句；仅当整行能放下时才合并测试与动作

## 函数与方法

- 函数保持 40 行以内；长函数拆分为更小、功能单一的函数
- 主程序代码必须在 `if __name__ == '__main__':` 块内
- `@classmethod` 仅用于命名构造器或修改全局状态；避免 `@staticmethod`
- 重写方法仅在行为实质变化或使用 `@override` 时才写 docstring

## 异常处理

- 使用内置异常如 `ValueError` 处理前置条件违反；自定义异常继承基类
- 不裸 `except:` 或 `except Exception:`，除非重新抛出或做隔离点
- `try` 块内代码最小化；用 `finally` 清理；优先用上下文管理器
- 不用 `assert` 处理关键逻辑——`assert` 不保证运行；用显式 `if` 语句

## 代码风格

- 缩进用 4 个空格；禁用制表符；括号内隐式续行
- 最大行长 80 字符（URL、长标志、导入、字符串常量除外）
- 不用分号；不留尾部空白；逗号和冒号后加空格，前不加
- 二元运算符（`==`、`and`、`or`）两侧各一个空格
- 括号、方括号、花括号内不加空格；函数调用括号前不加空格

## 字符串与格式化

- 字符串格式化用 f-string、`%` 或 `.format()`；不用 `+` 拼接
- 循环中积累字符串用列表 + `.join()` 或 `io.StringIO`，禁用 `+=`
- 多行字符串用三双引号；有缩进内容用 `textwrap.dedent()`
- 日志语句用 `%` 占位符字符串，不用 f-string 或已展开的格式字符串

## 集合与推导式

- 容器用默认迭代器：`for key in dict` 而非 `dict.keys()`；用 `in` 操作符
- 推导式只用于简单情况；多个 `for` 子句或复杂过滤禁用推导式
- 用生成器节省内存；docstring 用 `Yields:` 而非 `Returns:`

## 高级特性

- 避免元类、字节码操作、`__del__` 方法、过度反射等高级特性
- 可变全局状态最小化；模块级常量用 `CONSTANT_NAME`；可变全局变量加 `_` 前缀
- 闭包用词法作用域；多线程用 `queue.Queue` 和 `threading.Condition`
