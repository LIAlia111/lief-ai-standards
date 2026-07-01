# TypeScript 编码规范

## 版本与工具

- TypeScript >= 5.x
- 格式化：`prettier`（单引号，2 空格缩进，分号）
- Lint：`eslint` + `@typescript-eslint`
- 包管理：`pnpm`（首选）或 `npm`

## 严格模式

tsconfig.json 必须开启：
```json
{
  "compilerOptions": {
    "strict": true,
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true
  }
}
```

## 类型规范

```typescript
// ✅ 用 interface 定义对象形状
interface User {
  id: number
  name: string
  email: string
}

// ✅ 用 type 定义联合/交叉类型
type Status = "active" | "inactive" | "pending"

// ❌ 不用 any，用 unknown 然后做类型收窄
function parse(data: unknown): User {
  if (!isUser(data)) throw new Error("Invalid user")
  return data
}
```

## 异步

```typescript
// ✅ async/await，不用裸 Promise.then 链
async function fetchUser(id: number): Promise<User> {
  const res = await fetch(`/api/users/${id}`)
  if (!res.ok) throw new Error(`HTTP ${res.status}`)
  return res.json() as Promise<User>
}
```

## 模块导入顺序

1. Node 内置（`path`, `fs`）
2. 第三方库（`react`, `express`）
3. 内部绝对路径（`@/lib/...`）
4. 相对路径（`./utils`）

## React（如适用）

- 组件用函数式 + hooks，不用 class
- Props 用 interface 声明，不用 type
- 副作用写在 useEffect，不写在 render 里
