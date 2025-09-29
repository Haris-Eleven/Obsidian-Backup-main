1. Javascript with types to detect errors during compilation.
# Basic
``` typescript
// Primitives
let age: number = 25;
let name: string = 'Alice';
let isActive: boolean = true;

// Arrays
let numbers: number[] = [1, 2, 3];
let strings: Array<string> = ['a', 'b']; // same as string[]

// Tuples
let person: [string, number] = ['Alice', 25];

// Enums
enum Direction {
  Up,
  Down,
  Left,
  Right
}

// Any (avoid this when possible)
let randomValue: any = 'hello';

// Unknown (safer than any)
let input: unknown = 'test';

// Null and Undefined
let nothing: null = null;
let notDefined: undefined = undefined;
```
# Functions 
``` typescript
function add(a: number, b: number): number {
  return a + b;
}

// Optional parameter
function greet(name?: string): void {
  console.log(`Hello ${name ?? 'Guest'}`);
}

// Arrow function
const multiply = (a: number, b: number): number => a * b;

```
# Interfaces
``` typescript
interface User {
  id: number;
  name: string;
  isAdmin?: boolean; // optional property
}

const user: User = {
  id: 1,
  name: 'Alice',
};

```
# Generics 
- **Generics** let you create reusable components or functions that work with any type.
``` ts
function identity<T>(value: T): T {
  return value;
}

let output1 = identity<string>('hello'); // T = string
let output2 = identity<number>(123);     // T = number

```
# Type Assertions
```ts
let someValue: any = 'this is a string';

let strLength: number = (someValue as string).length;

// or with <>
let strLength2: number = (<string>someValue).length;

```
