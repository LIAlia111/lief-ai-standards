# Java 编码规范

> 来源：[Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)

## 文件结构

- 源文件用 UTF-8 编码，扩展名 `.java`
- 每个源文件只有一个顶级类，类名与文件名一致
- 文件结构顺序：许可证 → 包声明 → 导入 → 类声明，各部分之间空一行

## 导入

- 不用通配符导入；所有导入明确列出
- 静态导入和非静态导入分组，组间空一行
- 组内导入按 ASCII 顺序排列
- 导入行不换行，不受列数限制

## 格式化

- 列限制 100 字符
- 缩进用 +2 空格；禁用制表符
- 非空块遵循 K&R 风格：左括号前不换行，后换行；右括号独占行
- 空块可简写 `{}`（`if/else` 等多块语句中除外）
- 每行一条语句

## 空白

- 关键字（`if`/`for`/`while` 等）与 `(` 之间加一个空格
- 二元/三元运算符两侧各加一个空格
- 逗号、分号、右括号后加空格
- 点分隔符、方法引用 `::` 不加空格

## 命名规范

- 包名：全小写加数字，如 `com.example.deepspace`
- 类名：`UpperCamelCase`，通常为名词或名词短语
- 方法名：`lowerCamelCase`，通常为动词或动词短语
- 常量名：`UPPER_SNAKE_CASE`（`static final` 且深层不可变）
- 字段名：`lowerCamelCase`（常量除外）
- 参数名：`lowerCamelCase`；公开方法避免单字符参数名
- 局部变量名：`lowerCamelCase`，不作为常量处理
- 类型变量：单大写字母或「名词 + T」形式

## 控制流

- `if/else/for/do/while` 必须用花括号，即使单语句
- 续行至少缩进 +4 空格

## Switch

- 新式 switch 用箭头 `->`；旧式用冒号 `:`
- 旧式 switch fall-through 必须注释 `// fall through`
- 所有 switch 必须穷举（含 `default` 标签）

## 注解

- 类/包/模块注解：文档块后独占一行，每个注解一行
- 字段注解：多个可写同一行

## 注释

- 块注释与代码同缩进
- TODO 格式：`// TODO: bug_url - 解释说明`
- 实现注释说明「为什么」，不说「做什么」
- 被捕获的异常不能忽略；必须记日志或重新抛出

## 编程实践

- 方法重写必须加 `@Override`（`@Deprecated` 父类除外）
- 静态成员通过类名引用，不通过实例
- 禁止使用 `finalize` 方法
