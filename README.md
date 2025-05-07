# About Typescript
## 🔑 `keyof` in TypeScript

The `keyof` keyword is used to get a **union type** of all property names (keys) of a given type.

### ✅ Example
```ts
type Person = {
  name: string;
  age: number;
};

type PersonKeys = keyof Person;
// PersonKeys is "name" | "age"

