# C++ 编码规范

> 来源：[Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)

## 命名规范

- 常量名用 `kConstantName`（k 前缀 + 驼峰）
- 变量名用 `lower_with_under` 小写下划线
- 函数名用 `PascalCase` 驼峰：`FunctionName()`
- 类名用 `ClassName`，不含下划线
- 命名空间基于项目名创建，避免冲突

## 头文件

- 每个 `.cc` 文件配套 `.h` 头文件（单元测试和 `main` 函数除外）
- 头文件必须自包含（能独立编译），自己包含所需的其他头文件
- 头文件用 `#define` 防护：`PROJECT_PATH_FILE_H_`
- 包含顺序：相关头文件 → C 系统头文件 → C++ 标准库 → 第三方库 → 项目头文件
- 各组之间空行分隔；组内按字母顺序
- 避免前向声明；优先 `#include` 完整头文件
- 头文件内不写 `using namespace` 或命名空间别名（`internal` 除外）

## 类设计

- 类数据成员必须是 `private`（常量除外）
- 构造函数内不调用虚函数，不做可能失败的初始化
- 隐式类型转换用 `explicit` 防止（copy/move 构造函数除外）
- 明确声明类的可复制性：`= default` 或 `= delete`
- 函数约 40 行以内；优先写短小聚焦的函数
- 优先通过返回值传出数据，不用输出参数
- 函数参数顺序：输入参数在前，输出参数在后

## 内存管理

- 禁止使用动态初始化的全局/静态变量，仅允许平凡析构函数的对象
- 全局变量必须满足 `constexpr` 初始化
- 函数作用域内的静态变量可用动态初始化

## 智能指针

- 独占所有权用 `std::unique_ptr`
- 共享所有权用 `std::shared_ptr`（仅在必要时）
- 禁用 `std::auto_ptr`，改用 `std::unique_ptr`
- 全局/静态变量中避免智能指针（非平凡析构函数）

## 命名空间

- 代码放入命名空间，避免污染全局命名空间
- 禁用 `using namespace foo` 指令
- `.cc` 文件内仅供本文件使用的定义用内部链接（`static` 或匿名命名空间）

## 变量声明

- 在最小必要作用域内声明变量，靠近首次使用处
- 声明时初始化；循环变量在 `for`/`while` 中声明

## 现代 C++ 特性

- 代码目标 C++20，不用 C++23 特性
- 右值引用仅用于：move 构造/赋值、完美转发、`&&` 限定方法
- 类型转换优先用：brace 初始化 / `static_cast` / `const_cast`；禁用 C 风格 cast
- 避免 RTTI（`typeid`、`dynamic_cast`）；优先虚函数或访问者模式

## 异常与错误处理

- 禁用 C++ 异常
- `noexcept` 仅用于 move 构造函数或能准确反映语义时

## 继承与多态

- 继承用 `public`；优先组合而非继承
- 覆盖虚函数用 `override` 或 `final`（不再写 `virtual`）
- 运算符重载需语义明确；避免重载 `&&`、`||`、`,`

## 工具

- 用 `cpplint.py` 检查代码风格
