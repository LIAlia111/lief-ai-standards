# 通用编码规范

适用所有语言/框架的基础规范。

## 代码风格

- 缩进：Python 用 4 空格，JS/TS 用 2 空格
- 行长：最多 100 字符
- 空行：函数之间 1 行空行，逻辑块之间 1 行空行
- 字符串：Python 用双引号，JS/TS 用单引号（模板字符串用反引号）

## 命名规范

| 场景 | 风格 | 示例 |
|---|---|---|
| Python 变量/函数 | snake_case | `get_user_by_id` |
| Python 类 | PascalCase | `UserRepository` |
| JS/TS 变量/函数 | camelCase | `getUserById` |
| JS/TS 类/类型 | PascalCase | `UserRepository` |
| 常量 | UPPER_SNAKE_CASE | `MAX_RETRY_COUNT` |
| 文件名 | kebab-case | `user-service.ts` |

## 函数规范

- 单函数不超过 40 行（超过就拆）
- 参数不超过 4 个（超过就用对象/dataclass 封装）
- 返回类型明确（Python 用类型注解，TS 用类型声明）

## 错误处理

- 外部调用（API / IO / DB）必须有 try-catch
- 错误信息要能定位问题，不能只写 "Error occurred"
- 不用空 catch 块吞掉异常

## 测试

- 每个公共函数至少一个正向用例 + 一个边界用例
- Mock 外部依赖，不在单测里真实调用 API/DB
- 测试命名：`test_<功能>_<场景>_<预期结果>`
