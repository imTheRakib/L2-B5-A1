# Blog of keyof and enum
## keyof in TypeScript

The keyof operator in TypeScript is a type operator that creates a union type of all known, public property names of a given type.

### Example
```typescript
interface Dog {
  name: string;
  age: number;
  breed: string;
}

// keyof creates a union type of all property names
type DogKeys = keyof Dog; 
// Equivalent to: "name" | "age" | "breed"

function printDogInfo(dog: Dog, key: DogKeys) {
  console.log(`${key}: ${dog[key]}`);
}

const myDog: Dog = {
  name: "Rex",
  age: 3,
  breed: "Golden Retriever"
};

// These work because the keys exist on Dog
printDogInfo(myDog, "name");  // Output: "name: Rex"
printDogInfo(myDog, "age");   // Output: "age: 3"

// This would cause a TypeScript error because "color" isn't a Dog property
// printDogInfo(myDog, "color");  // Error!
```
## Enums in TypeScript

In TypeScript, **enums** are a way to define a set of named constants. These constants can be either numeric or string-based. Enums help to create a meaningful set of values that can be used in your code for readability and maintainability.

There are two types of enums in TypeScript:

1. **Numeric Enums**: The members of a numeric enum are automatically assigned incremental values, starting from 0 by default.

2. **String Enums**: The members of a string enum are manually assigned string values.

### Numeric Enum Example
```typescript
enum Direction {
  Up = 1,
  Down,
  Left,
  Right
}

console.log(Direction.Up);    // Output: 1
console.log(Direction.Down);  // Output: 2
console.log(Direction.Left);  // Output: 3
console.log(Direction.Right); // Output: 4
```
### String Enum Example
```typescript
enum Status {
  Pending = "PENDING",
  InProgress = "IN_PROGRESS",
  Completed = "COMPLETED"
}

console.log(Status.Pending);     // Output: "PENDING"
console.log(Status.InProgress);  // Output: "IN_PROGRESS"
console.log(Status.Completed);   // Output: "COMPLETED"
```

