# JavaScript Import and Export Examples

## Exporting

```js
// file: mathUtils.js
export function add(a, b) {
	return a + b;
}

export const PI = 3.14159;

// Exporting multiple at once
function subtract(a, b) {
	return a - b;
}
export { subtract };
```

## Importing

```js
// file: app.js
import { add, PI, subtract } from './mathUtils.js';

console.log(add(2, 3)); // 5
console.log(PI);        // 3.14159
console.log(subtract(5, 2)); // 3
```

### Spread Operators 
spread operators are used to expand elements of an iterable (like an array) into individual elements.

```js
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];
console.log(arr2); 

// output: [1, 2, 3, 4, 5]
```

```js
const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 };
console.log(obj2); 

// output: { a: 1, b: 2, c: 3 }
```

```js
const arr1 = [1, 2, 3];
const [a, b, c] = [...arr1];
console.log(a, b, c);

// output: 1 2 3
```

```js
function sum(x, y, z) {
	return x + y + z;
}
const arr1 = [1, 2, 3];
console.log(sum(...arr1)); 

// output: 6
```