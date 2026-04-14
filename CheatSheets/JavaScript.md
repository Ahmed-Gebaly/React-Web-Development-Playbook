# 📚 JavaScript Notes

---

## 📄 What is JavaScript?

**JavaScript (JS)** is a lightweight, interpreted programming language for web development. It enables interactive, dynamic web pages and runs in browsers and **Node.js** (server-side).

### Key Points:
- **Interpreted**: Executed directly by browsers (no compilation)
- **Dynamically Typed**: Variables can hold any data type
- **Event-Driven**: Responds to user interactions
- **Object-Oriented & Functional**: Both programming paradigms supported

> **📌 Note**: JavaScript is standardized by **ECMAScript (ES)**. Most modern code uses **ES6+ (2015 onwards)**.

---

## 💻 How to Write JavaScript?

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Method</th>
    <th>Location</th>
    <th>Use Case</th>
  </tr>
  <tr>
    <td><strong>Inline</strong></td>
    <td>Inside `&lt;script&gt;` tag in HTML</td>
    <td>Quick tests, small scripts</td>
  </tr>
  <tr>
    <td><strong>External File</strong></td>
    <td>Separate `.js` file linked in HTML</td>
    <td>Production code, best practice</td>
  </tr>
  <tr>
    <td><strong>Browser Console</strong></td>
    <td>DevTools (F12 → Console)</td>
    <td>Debugging, testing</td>
  </tr>
</table>

### 1️⃣ Inline
```html
<!DOCTYPE html>
<html>
<body>
  <h1>Hello</h1>
  <script>
    console.log('This runs inline');
    let x = 10;
    alert(x);
  </script>
</body>
</html>
```

### 2️⃣ External File
**index.html**
```html
<script src="app.js"></script>
```

**app.js**
```js
console.log('From external file');
function greet(name) {
  return `Hello, ${name}!`;
}
```

### 3️⃣ Browser Console
Press `F12` → **Console** tab → Type:
```js
console.log('Test');
let result = 5 + 10;
console.log(result);
```

## 🧩 Core Concepts
- **Variables**: `var`, `let`, `const`
- **Data Types**: `string`, `number`, `boolean`, `object`, `undefined`, `null`, `symbol`
- **Functions**: Regular, Arrow, Anonymous
- **Control Flow**: `if`, `else`, `switch`, loops (`for`, `while`)
- **Objects & Arrays**: Key-value pairs and ordered collections
- **Asynchronous Programming**: Promises, `async/await`, callbacks
- **Modules**: Importing and exporting code across files
- **DOM Manipulation**: Interacting with HTML elements
- **Event Handling**: Responding to user actions (clicks, input, etc.)
- **Error Handling**: `try`, `catch`, `finally`
- **ES6+ Features**: Template literals, destructuring, default parameters, etc.

## ⚙️ JavaScript Function Types

JavaScript functions are a core part of the language and can be created in different forms. Use this section to understand the main function categories and their role.

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Function Type</th>
    <th>Definition</th>
    <th>Key Behavior</th>
    <th>Typical Use</th>
  </tr>
  <tr>
    <td><strong>Function Declaration</strong></td>
    <td>A named function defined with the `function` keyword.</td>
    <td>Hoisted; available before declaration.</td>
    <td>Reusable named logic and core application behavior.</td>
  </tr>
  <tr>
    <td><strong>Function Expression</strong></td>
    <td>A function assigned to a variable or constant.</td>
    <td>Created at runtime; not hoisted like declarations.</td>
    <td>Flexible function assignment and conditional definition.</td>
  </tr>
  <tr>
    <td><strong>Arrow Function</strong></td>
    <td>Shorter syntax using `=>` for function creation.</td>
    <td>Uses lexical `this`; no `arguments` object.</td>
    <td>Compact callbacks and functions inside expressions.</td>
  </tr>
  <tr>
    <td><strong>Generator Function</strong></td>
    <td>Function that can pause and resume execution with `yield`.</td>
    <td>Returns an iterator and supports sequence control.</td>
    <td>Iterating values lazily and custom iteration flows.</td>
  </tr>
  <tr>
    <td><strong>Async Function</strong></td>
    <td>Function defined with `async` that returns a Promise.</td>
    <td>Allows `await` and asynchronous code in a synchronous style.</td>
    <td>Handling asynchronous operations and API calls cleanly.</td>
  </tr>
  <tr>
    <td><strong>Method</strong></td>
    <td>Function defined as a property of an object.</td>
    <td>Called on an object; `this` refers to the owning object.</td>
    <td>Encapsulating behavior within objects and classes.</td>
  </tr>
  <tr>
    <td><strong>Constructor Function</strong></td>
    <td>Function used with `new` to create object instances.</td>
    <td>Initializes object state and returns a new instance.</td>
    <td>Creating reusable object templates and custom types.</td>
  </tr>
</table>

## 🧠 JavaScript Function Features

Functions in JavaScript offer powerful features that support modular, maintainable code.

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Feature</th>
    <th>What It Means</th>
    <th>Why It Matters</th>
  </tr>
  <tr>
    <td><strong>First-class functions</strong></td>
    <td>Functions are treated like values and can be stored, passed, and returned.</td>
    <td>Enables higher-order programming and flexible abstractions.</td>
  </tr>
  <tr>
    <td><strong>Higher-order functions</strong></td>
    <td>Functions that accept functions as arguments or return functions.</td>
    <td>Useful for callbacks, array processing, and function composition.</td>
  </tr>
  <tr>
    <td><strong>Closures</strong></td>
    <td>Functions retain access to variables from their defining scope.</td>
    <td>Supports private state and encapsulation inside functions.</td>
  </tr>
  <tr>
    <td><strong>Default parameters</strong></td>
    <td>Function parameters can have default values if not provided.</td>
    <td>Makes function calls simpler and safer by avoiding `undefined`.</td>
  </tr>
  <tr>
    <td><strong>Rest parameters</strong></td>
    <td>Collects remaining arguments into an array.</td>
    <td>Supports variable argument lengths cleanly.</td>
  </tr>
  <tr>
    <td><strong>Spread syntax</strong></td>
    <td>Expands iterable values into individual arguments or elements.</td>
    <td>Helps merge arrays, pass arguments, and clone data easily.</td>
  </tr>
  <tr>
    <td><strong>`this` binding</strong></td>
    <td>Determines what object `this` refers to inside a function.</td>
    <td>Important for methods, constructors, and arrow function behavior.</td>
  </tr>
  <tr>
    <td><strong>Async/await</strong></td>
    <td>Simplifies asynchronous code by waiting for Promises.</td>
    <td>Produces clearer async flow than nested callbacks or `.then()` chains.</td>
  </tr>
  <tr>
    <td><strong>Function properties</strong></td>
    <td>Functions have metadata like `name`, `length`, and `prototype`.</td>
    <td>Useful for introspection, debugging, and class-style behavior.</td>
  </tr>
</table>

## 📝 Variables and Data Types

### 🏷️ What are Variables?

A **variable** is a named container that stores data values. You declare variables using `let`, `const`, or `var`.

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Keyword</th>
    <th>Scope</th>
    <th>Reassignable</th>
    <th>Use Case</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>let</strong></td>
    <td>Block</td>
    <td>Yes</td>
    <td>Modern standard</td>
    <td><code>let age = 25;</code></td>
  </tr>
  <tr>
    <td><strong>const</strong></td>
    <td>Block</td>
    <td>No</td>
    <td>Values that don't change</td>
    <td><code>const PI = 3.14;</code></td>
  </tr>
  <tr>
    <td><strong>var</strong></td>
    <td>Function</td>
    <td>Yes</td>
    <td>Avoid (old syntax)</td>
    <td><code>var name = 'John';</code></td>
  </tr>
</table>

> **✅ Best Practice**: Use `const` by default, `let` when you need to reassign.

### 📦 Data Types

JavaScript has **8 main data types**:

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Data Type</th>
    <th>Definition</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>String</strong></td>
    <td>Text data enclosed in quotes (' ' or " ") or backticks (` `)</td>
    <td><code>let msg = "Hello";</code><br/><code>let name = 'John';</code><br/><code>let greeting = `Hi ${name}`;</code></td>
  </tr>
  <tr>
    <td><strong>Number</strong></td>
    <td>Integer or decimal numbers</td>
    <td><code>let age = 25;</code><br/><code>let price = 19.99;</code><br/><code>let result = Infinity;</code></td>
  </tr>
  <tr>
    <td><strong>Boolean</strong></td>
    <td>True or False values (used in conditions)</td>
    <td><code>let isActive = true;</code><br/><code>let isEmpty = false;</code></td>
  </tr>
  <tr>
    <td><strong>Array</strong></td>
    <td>Ordered collection of values inside [ ]</td>
    <td><code>let colors = ['red', 'blue', 'green'];</code><br/><code>let numbers = [1, 2, 3, 4];</code></td>
  </tr>
  <tr>
    <td><strong>Object</strong></td>
    <td>Key-value pairs inside { }</td>
    <td><code>let person = { name: 'John', age: 25, city: 'NYC' };</code></td>
  </tr>
  <tr>
    <td><strong>Undefined</strong></td>
    <td>Variable declared but no value assigned</td>
    <td><code>let x;</code><br/><code>console.log(x); // undefined</code></td>
  </tr>
  <tr>
    <td><strong>Null</strong></td>
    <td>Intentional absence of value (assigned manually)</td>
    <td><code>let empty = null;</code></td>
  </tr>
  <tr>
    <td><strong>Symbol</strong></td>
    <td>Unique identifier (ES6+, advanced)</td>
    <td><code>let id = Symbol('userId');</code></td>
  </tr>
</table>

### how to define a variable?

```js
data_type variable_name = value;
```

### 💡 Examples

**Declaring Variables:**
```js
// String
const firstName = "Alice";
let lastName = "Johnson";

// Number
const age = 28;
const salary = 50000.50;

// Boolean
const isStudent = false;
const isEmployed = true;

// Array
const fruits = ['apple', 'banana', 'orange'];
const scores = [85, 90, 78, 92];

// Object
const user = {
  name: "Bob",
  age: 30,
  email: "bob@example.com"
};

// Undefined
let result;
console.log(result); // undefined

// Null
let noValue = null;
```

**Accessing Values:**
```js
// String
console.log(firstName); // Alice

// Array (using index, starts at 0)
console.log(fruits[0]); // apple

// Object (using key)
console.log(user.name); // Bob
console.log(user['email']); // bob@example.com

// Type checking
console.log(typeof age); // number
console.log(typeof firstName); // string
console.log(typeof isStudent); // boolean
console.log(typeof fruits); // object
```

### how to check data type?
```js
let name = "Alice";
console.log(typeof name); // string
let age = 30;
console.log(typeof age); // number
let isStudent = false;
console.log(typeof isStudent); // boolean
let fruits = ['apple', 'banana'];
console.log(typeof fruits); // object (arrays are a type of object)
let user = { name: "Bob", age: 25 };
console.log(typeof user); // object
let result;
console.log(typeof result); // undefined
let noValue = null;
console.log(typeof noValue); // object (this is a quirk in JavaScript)
```	

### 🧩 Variable Scope
- **Global Scope**: Accessible anywhere in the code
- **Function Scope**: Accessible only within the function
- **Block Scope**: Accessible only within the block (e.g., inside `{ }`)

```js
function test() {
  let functionScoped = "I am inside a function";
  if (true) {
	let blockScoped = "I am inside a block";
	console.log(functionScoped); // Accessible
	console.log(blockScoped); // Accessible
  }
  console.log(blockScoped); // Error: blockScoped is not defined
}
test();
console.log(functionScoped); // Error: functionScoped is not defined
```
**Hoisting**: `var` declarations are hoisted to the top of their scope, but `let` and `const` are not.

```js
console.log(x); // undefined (due to hoisting)
var x = 5;
console.log(y); // Error: Cannot access 'y' before initialization
let y = 10;
```

### 🧩 Variable Mutability
- **Mutable**: `let` variables can be reassigned
- **Immutable**: `const` variables cannot be reassigned (but objects/arrays declared with `const` can still be modified)

```js
const PI = 3.14;
PI = 3.14159; // Error: Assignment to constant variable
const user = { name: "Alice", age: 25 };
user.age = 26; // Allowed (modifying object properties)
console.log(user); // { name: "Alice", age: 26 }
```

### 🧩 Variable Naming Conventions

- Use **camelCase** for variables and functions (e.g., `firstName`, `calculateTotal`)
- Use **PascalCase** for classes (e.g., `User`, `Product`)
- Avoid using reserved keywords (e.g., `var`, `function`, `class`)
- Use meaningful names that describe the purpose of the variable (e.g., `isLoggedIn` instead of `x`)
- Start variable names with a letter, underscore (_), or dollar sign ($); avoid starting with numbers (e.g., `1stName` is invalid)
- Be consistent with naming conventions throughout your codebase for better readability and maintainability.
- Use `const` for values that should not change and `let` for values that will be reassigned to prevent accidental mutations and improve code clarity.
- Avoid using `var` as it has function scope and can lead to unexpected behavior due to hoisting; prefer `let` and `const` for block-scoped variables.
- Use descriptive names for variables to enhance code readability and maintainability, making it easier for others (or yourself in the future) to understand the purpose of each variable at a glance.
- Consider using prefixes for boolean variables (e.g., `is`, `has`, `can`) to indicate their true/false nature, improving code readability and making it clear that the variable represents a condition or state.
- Use uppercase letters with underscores for constants (e.g., `MAX_USERS`, `API_KEY`) to differentiate them from regular variables and indicate that their values should not change throughout the program.
- Avoid using single-letter variable names (e.g., `x`, `y`, `z`) except in very short loops or mathematical contexts, as they can be ambiguous and reduce code readability; instead, opt for descriptive names that convey the variable's purpose or meaning.
- Use plural names for arrays (e.g., `users`, `items`) to indicate that the variable holds a collection of values, making it easier to understand the data structure being used.
- Consider using namespaces or modules to group related variables and functions together, especially in larger codebases, to avoid naming collisions and improve code organization.
- Use comments to explain the purpose of complex variables or to provide context for their usage, especially if the variable name alone does not fully convey its intent or if it is part of a larger algorithm or logic.
- Regularly review and refactor variable names as your code evolves to ensure they remain accurate and descriptive, enhancing the overall readability and maintainability of your codebase.
- Adhering to consistent variable naming conventions and best practices can significantly improve the clarity and maintainability of your code, making it easier for you and others to understand and work with your JavaScript projects effectively.
  

### 🧩 Constants
A **constant** is a variable that cannot be reassigned after its initial value is set. In JavaScript, you can declare constants using the `const` keyword.

```js
const PI = 3.14159;
PI = 3.14; // Error: Assignment to constant variable
```	

### arthmetic operators

---

## 🔍 Comparison Operators: == vs === vs != vs !==

This is a **critical concept** for beginners. Understanding the difference can prevent bugs!

### 📊 Quick Comparison Table

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Operator</th>
    <th>Name</th>
    <th>Type Coercion</th>
    <th>Example</th>
    <th>Result</th>
  </tr>
  <tr>
    <td><strong>==</strong></td>
    <td>Loose Equality</td>
    <td>Yes (converts types)</td>
    <td><code>5 == '5'</code></td>
    <td><code>true</code> ⚠️</td>
  </tr>
  <tr>
    <td><strong>===</strong></td>
    <td>Strict Equality</td>
    <td>No (checks type too)</td>
    <td><code>5 === '5'</code></td>
    <td><code>false</code> ✅</td>
  </tr>
  <tr>
    <td><strong>!=</strong></td>
    <td>Loose Inequality</td>
    <td>Yes (converts types)</td>
    <td><code>5 != '5'</code></td>
    <td><code>false</code> ⚠️</td>
  </tr>
  <tr>
    <td><strong>!==</strong></td>
    <td>Strict Inequality</td>
    <td>No (checks type too)</td>
    <td><code>5 !== '5'</code></td>
    <td><code>true</code> ✅</td>
  </tr>
</table>

### 🎯 Key Difference

- **`==` (Loose)**: Compares *values* only, converts types if needed
- **`===` (Strict)**: Compares *values AND types*, no conversion

### 💡 Examples

```js
// == (Loose Equality - Type Conversion Happens)
console.log(5 == '5');          // true (number 5 == string '5')
console.log(0 == false);        // true (0 == false)
console.log(1 == true);         // true (1 == true)
console.log(null == undefined); // true (considered equal)
console.log('0' == false);      // true (string '0' == false)

// === (Strict Equality - No Type Conversion)
console.log(5 === '5');         // false (different types)
console.log(0 === false);       // false (different types)
console.log(1 === true);        // false (different types)
console.log(null === undefined);// false (different types)
console.log('0' === false);     // false (different types)

// != (Loose Inequality)
console.log(5 != '5');          // false (they're equal when converted)
console.log(10 != '5');         // true (different values)

// !== (Strict Inequality)
console.log(5 !== '5');         // true (different types)
console.log(5 !== 5);           // false (same value and type)
console.log(10 !== '5');        // true (different values and types)
```

### ⚠️ Common Gotchas

```js
// Unexpected behavior with ==
console.log('' == 0);           // true (empty string converts to 0)
console.log('  ' == 0);         // true (whitespace converts to 0)
console.log(NaN == NaN);        // false (NaN is never equal to anything)
console.log('5' == 5);          // true (automatic conversion)

// Strict equality avoids these issues
console.log('' === 0);          // false
console.log('  ' === 0);        // false
console.log(NaN === NaN);       // false
console.log('5' === 5);         // false
```

### ✅ Best Practice

> **Always use `===` and `!==`** in your code. They are safer and prevent unexpected behavior from type coercion.

```js
if (userAge === 18) {           // ✅ Good
  console.log('You are 18');
}

if (userAge == 18) {            // ⚠️ Avoid
  console.log('You are 18');
}
```























---

## 🌐 Displaying JavaScript Output in HTML (DOM Manipulation)

Instead of just using `console.log()`, you can display JavaScript output directly on the web page using **DOM (Document Object Model)** methods.

### 📊 Common Methods

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Method</th>
    <th>Purpose</th>
    <th>Example</th>
    <th>Returns HTML?</th>
  </tr>
  <tr>
    <td><strong>innerHTML</strong></td>
    <td>Replace/insert HTML content</td>
    <td><code>element.innerHTML = "&lt;p&gt;Hello&lt;/p&gt;";</code></td>
    <td>Yes</td>
  </tr>
  <tr>
    <td><strong>textContent</strong></td>
    <td>Insert plain text only</td>
    <td><code>element.textContent = "Hello";</code></td>
    <td>No (safer)</td>
  </tr>
  <tr>
    <td><strong>getElementById()</strong></td>
    <td>Select element by ID</td>
    <td><code>document.getElementById("id")</code></td>
    <td>Returns element</td>
  </tr>
  <tr>
    <td><strong>createElement()</strong></td>
    <td>Create new HTML element</td>
    <td><code>document.createElement("p")</code></td>
    <td>Returns new element</td>
  </tr>
  <tr>
    <td><strong>appendChild()</strong></td>
    <td>Add element as child</td>
    <td><code>parent.appendChild(child)</code></td>
    <td>Adds to DOM</td>
  </tr>
</table>

### 💡 Step-by-Step Examples

**Step 1: Create an HTML element with an ID**
```html
<div id="output"></div>
<div id="results"></div>
```

**Step 2: Use JavaScript to display content**

```js
// Method 1: innerHTML - Insert HTML content
var output = document.getElementById("output");
output.innerHTML = "<h3>Calculator Results</h3>";
output.innerHTML += "<p>Sum: " + (5 + 10) + "</p>";

// Method 2: textContent - Insert plain text (safer)
var results = document.getElementById("results");
results.textContent = "The sum is: " + (5 + 10);

// Method 3: Create and append elements
var newPara = document.createElement("p");
newPara.textContent = "This paragraph was created dynamically";
results.appendChild(newPara);

// Method 4: Using template literals (modern way)
var num1 = 25;
var num2 = 15;
output.innerHTML += `
  <h4>Calculation</h4>
  <p>Number 1: ${num1}</p>
  <p>Number 2: ${num2}</p>
  <p>Sum: ${num1 + num2}</p>
`;
```

### 🎯 Practical Example

**HTML:**
```html
<div id="calculator"></div>
```

**JavaScript:**
```js
var a = 10;
var b = 5;
var calc = document.getElementById("calculator");

calc.innerHTML = `
  <h3>Simple Calculator</h3>
  <p><strong>${a} + ${b} = ${a + b}</strong></p>
  <p><strong>${a} - ${b} = ${a - b}</strong></p>
  <p><strong>${a} * ${b} = ${a * b}</strong></p>
  <p><strong>${a} / ${b} = ${a / b}</strong></p>
`;
```

### ⚠️ innerHTML vs textContent

```js
var element = document.getElementById("output");

// innerHTML - Interprets HTML tags
element.innerHTML = "<strong>Bold Text</strong>";  // Shows bold text
element.innerHTML = "<script>alert('Hi')</script>"; // Can be unsafe!

// textContent - Treats everything as plain text
element.textContent = "<strong>Bold Text</strong>";  // Shows literal text: <strong>Bold Text</strong>
element.textContent = "<script>alert('Hi')</script>"; // Safe - shows as text, doesn't execute
```

### ✅ Best Practices

> **Use `textContent` for simple text** - It's safer and prevents code injection
> **Use `innerHTML` only for HTML formatting** - Be careful with user input
> **Always use `getElementById()` with proper IDs** - Avoid inline scripts when possible

---

## 🎯 Controlling Element Position & Location

Different methods place elements in **different locations**. Understanding where elements appear is crucial!

### 📊 Method Comparison - Where Elements Go

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Method</th>
    <th>Location</th>
    <th>Requires ID?</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><strong>appendChild()</strong></td>
    <td>INSIDE element, at the END (last child)</td>
    <td>Yes</td>
    <td><code>element.appendChild(newChild)</code></td>
  </tr>
  <tr>
    <td><strong>insertAdjacentHTML("afterbegin")</strong></td>
    <td>INSIDE element, at the START (first child)</td>
    <td>Yes</td>
    <td><code>element.insertAdjacentHTML("afterbegin", html)</code></td>
  </tr>
  <tr>
    <td><strong>insertAdjacentHTML("beforeend")</strong></td>
    <td>INSIDE element, at the END (last child)</td>
    <td>Yes</td>
    <td><code>element.insertAdjacentHTML("beforeend", html)</code></td>
  </tr>
  <tr>
    <td><strong>insertAdjacentHTML("beforebegin")</strong></td>
    <td>OUTSIDE element, BEFORE it</td>
    <td>Yes</td>
    <td><code>element.insertAdjacentHTML("beforebegin", html)</code></td>
  </tr>
  <tr>
    <td><strong>insertAdjacentHTML("afterend")</strong></td>
    <td>OUTSIDE element, AFTER it</td>
    <td>Yes</td>
    <td><code>element.insertAdjacentHTML("afterend", html)</code></td>
  </tr>
</table>

### 🎨 Visual Guide - insertAdjacentHTML Positions

```
<!-- beforebegin -->        ← OUTSIDE (above)
<div id="target">
  <!-- afterbegin -->       ← INSIDE (at the top)
  ...existing content...
  <!-- beforeend -->        ← INSIDE (at the bottom)
</div>
<!-- afterend -->           ← OUTSIDE (below)
```

### 💡 When Elements Need IDs

**You MUST have an ID** to target an element:

```html
<!-- ❌ No ID = Can't control where to put things -->
<div>Output here</div>

<!-- ✅ Has ID = Can target and control -->
<div id="output">Output here</div>
```

**JavaScript:**
```js
// ✅ Correct - Element has an ID
var output = document.getElementById("output");
output.innerHTML = "New content";  // Replaces content inside #output

// ❌ Wrong - No ID, can't target it
var randomDiv = document.getElementById("nonexistent");  // Returns null, error!
```

### 🎯 Location Control Examples

**HTML:**
```html
<div id="container">
  <p>Original content</p>
</div>
```

**JavaScript:**
```js
var container = document.getElementById("container");

// 1. appendChild - Adds INSIDE at the END
var newP = document.createElement("p");
newP.textContent = "Added at the end";
container.appendChild(newP);
// Result: Original content + New paragraph

// 2. insertAdjacentHTML with "afterbegin" - INSIDE at START
container.insertAdjacentHTML("afterbegin", "<p>Added at the start</p>");
// Result: New paragraph + Original content + Previous new paragraph

// 3. insertAdjacentHTML with "beforebegin" - OUTSIDE before
container.insertAdjacentHTML("beforebegin", "<p>Added before container</p>");
// Result: Before container + Container (with all content) + After container

// 4. insertAdjacentHTML with "afterend" - OUTSIDE after
container.insertAdjacentHTML("afterend", "<p>Added after container</p>");
// Result: All previous + Container div + This new paragraph
```

### ⚠️ Why Results Appear in Different Places

```js
// These add to DOM in DIFFERENT locations:
var output = document.getElementById("output");
var results = document.getElementById("results");

// This appears INSIDE #output
output.innerHTML += "<p>In output div</p>";

// This appears INSIDE #results
results.innerHTML += "<p>In results div</p>";

// This appears at END of #results (INSIDE it)
results.appendChild(newElement);

// This appears BEFORE #results (OUTSIDE it)
results.insertAdjacentHTML("beforebegin", "<p>Before results</p>");
```

### ✅ Best Practices

> **Always use IDs** to precisely target where elements go
> **Use `appendChild()` or `beforeend`** to add at the end (most common)
> **Use `afterbegin`** when you want items to appear at the top
> **Use `beforebegin`/`afterend`** when adding OUTSIDE a container

---

## 📦 Modules (Import & Export)

### Exporting

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

### Importing

```js
// file: app.js
import { add, PI, subtract } from './mathUtils.js';

console.log(add(2, 3)); // 5
console.log(PI);        // 3.14159
console.log(subtract(5, 2)); // 3
```

---

## 🔄 Spread Operator

The spread operator (`...`) expands elements of an iterable (array/object) into individual elements.

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