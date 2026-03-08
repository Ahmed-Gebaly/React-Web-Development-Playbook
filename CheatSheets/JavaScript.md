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

