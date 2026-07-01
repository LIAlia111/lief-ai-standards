# TypeScript 编码规范

> 来源：[Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)

## 变量与声明

- 默认用 `const`；需重赋值时用 `let`；永远不用 `var`
- 每条声明语句声明一个变量，不用逗号分隔
- 构造后不再重赋值的属性标记 `readonly`

## 导入导出

- 只用命名导出，不用默认导出
- 用 `import type` 导入仅类型符号，加速开发环境编译
- 重导出类型时用 `export type`，支持逐文件编译
- 不用 TypeScript `namespace`；用独立 ES6 模块组织代码
- 用相对路径 `./foo` 做项目内导入；外部代码用绝对路径
- 大型 API 用命名空间导入；常用工具用命名导入
- 不用 `require()` 或 `import x = require()`；用 ES6 import

## 类型系统

- 用 `interface` 定义对象结构，优先于 `type alias`
- 简单数组类型用 `T[]` 语法；复杂表达式用 `Array<T>`
- 不滥用 `Pick<>`、`Partial<>` 等映射类型，简单 interface 能解决时用 interface
- 禁止用 `any`；用 `unknown` 代替不透明值，需要时再收窄类型
- 用 type assertion（`as Type`）必须附注释说明原因
- 简单类型依赖推断，不写多余注解；复杂函数显式写返回类型
- 泛型类型参数必须出现在函数参数中，不只出现在返回类型中
- 不用 `const enum`，用普通 `enum` 保证正确的 JS 运行时行为
- 不修改内置对象原型或构造函数属性
- 不用 `#private` 字段；用 TypeScript 的 `private` 可见性修饰符
- 优先用 `?` 可选字段，不用 `T | undefined` 联合类型

## 命名规范

- 变量、函数、方法、属性用 `lowerCamelCase`
- 类、接口、类型、枚举、类型参数用 `UpperCamelCase`
- 模块级不可变值和枚举成员用 `CONSTANT_CASE`
- 不用前置或尾部下划线
- 名称中不嵌入类型信息（类型系统已表达的不重复）
- 描述性命名，不缩写；10 行范围内可用单字母变量

## 函数与方法

- 顶层命名函数用函数声明，不用箭头函数
- 嵌套作用域和方法体用箭头函数，自动绑定 `this`
- 类上不用箭头函数属性，用显式方法调用

## 比较与控制流

- 只用 `===` 和 `!==`；唯一例外是用 `== null` 同时判断 null/undefined
- `switch` 语句始终有 `default` 分支（即使为空）
- 非空 `switch case` 必须以 `break`、`return` 或 `throw` 结束

## 字符串与类型转换

- 字符串字面量用单引号；复杂拼接用模板字面量
- 类型强转用 `String()` 和 `Boolean()`；禁用一元 `+`
- 用 `Number()` 并配合 `isFinite()` 检查；不用 `parseInt()` 或 `parseFloat()`
- 禁用 `eval()` 和 `Function(string)` 构造函数
- 禁用 `with` 关键字

## 数组与循环

- 禁用 `Array()` 或 `new Array()` 构造函数；用 `[]` 字面量
- 数组遍历用 `for...of`；类 dict 对象遍历用 `for...in` 但必须过滤
- 优先用 `Object.keys()` / `Object.values()` / `Object.entries()`

## 异常处理

- 只 `throw` Error 实例或其子类，不 throw 原始值
- `catch` 时假设类型为 `unknown`，访问属性前先收窄到 `Error`
- `try` 块聚焦于可能抛出的代码；安全操作移到 `try` 外
