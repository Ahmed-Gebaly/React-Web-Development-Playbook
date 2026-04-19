# 📚 JavaScript Notes

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
- **Variables Types**: `var`, `let`, `const`
- **Data Types**: `string`, `number`, `boolean`, `object`, `undefined`, `null`, `symbol`
- **Control Flow**: `if`, `else`, `switch`, loops (`for`, `while`)
- **Objects & Arrays**: Key-value pairs and ordered collections
- **Functions**: Regular, Arrow, Anonymous
- **Asynchronous Programming**: Promises, `async/await`, callbacks
- **Modules**: Importing and exporting code across files
- **DOM Manipulation**: Interacting with HTML elements
- **Event Handling**: Responding to user actions (clicks, input, etc.)
- **Error Handling**: `try`, `catch`, `finally`
- **ES6+ Features**: Template literals, destructuring, default parameters, etc.

## 📝 Variables and Data Types

### 🧩 What are Variables?

A **variable** is a named container used to store and access values in memory during program execution.

### 🧩 Variables Types

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
    <td>Yes ✅</td>
    <td>Modern standard, values that change</td>
    <td><code>let age = 25; age = 26;</code></td>
  </tr>
  <tr>
    <td><strong>const</strong></td>
    <td>Block</td>
    <td>No ❌</td>
    <td>Constants, values that don't change</td>
    <td><code>const PI = 3.14;</code></td>
  </tr>
  <tr>
    <td><strong>var</strong></td>
    <td>Function</td>
    <td>Yes ✅</td>
    <td>Avoid (old syntax, confusing scope)</td>
    <td><code>var name = 'John';</code></td>
  </tr>
</table>

> **✅ Best Practice**: Use `const` by default, `let` when you need to reassign. Avoid `var`.

### 🧩 Data Types

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

### 🧩 Declaring a Variable

```js
variable_type variable_name = value;
```

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

### 🧩 Check Variable Data Type (typeof Operator)
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
let globalVar = "I am global";
function test() {
  let functionScoped = "I am inside a function";
  if (true) {
	let blockScoped = "I am inside a block";
  console.log(globalVar); // Accessible
	console.log(functionScoped); // Accessible
	console.log(blockScoped); // Accessible
  }
  console.log(globalVar); // Accessible
  console.log(functionScoped); // Accessible
  console.log(blockScoped); // Error: blockScoped is not defined
}
test();
console.log(globalVar); // Accessible
console.log(functionScoped); // Error: functionScoped is not defined
```
**Hoisting**: `var` declarations are hoisted to the top of their scope, but `let` and `const` are not.

```js
console.log(x); // undefined (due to hoisting)
var x = 5;
console.log(y); // Error: Cannot access 'y' before initialization
let y = 10;
```

### 🧩 Reassigning Variable
- `let` and `var` variables can be reassigned
- `const` variables cannot be reassigned (but objects/arrays declared with `const` can still be modified)

```js
const PI = 3.14;
PI = 3.14159; // Error: Assignment to constant variable
const user = { name: "Alice", age: 25 };
user.age = 26; // Allowed (modifying object properties)
console.log(user); // { name: "Alice", age: 26 }

const numbers = [1, 2, 3];
numbers.push(4); // Allowed (modifying array)
numbers.pop(); // Allowed (modifying array)
```

### 🧩 Reassignable VS Mutable
- **Reassignable**: You can make the variable point to a new value (e.g., `let x = 5; x = 10;`)
- **Mutable**: You can modify the value of the variable without reassigning it (e.g., `const arr = [1, 2, 3]; arr.push(4);`)
- **Objects and arrays** are mutable, even when declared with `const`
- **Primitive types** (string, number, boolean) are immutable

### 🧩 Variable Naming Rules

- Variable names must start with a letter, underscore (_), or dollar sign ($).
- Variable names are case-sensitive (e.g., `myVar` and `myvar` are different).
- Variable names can contain letters, digits, underscores, or dollar signs.
- Variable names cannot be reserved keywords (e.g., var, let, const, if, else, etc.).
- Use **camelCase** for variables and functions → `firstName`, `getUserData()`
- Use **UPPER_SNAKE_CASE** for constants → `MAX_USERS`, `API_KEY`
- Use **PascalCase** for classes → `UserService`, `DataModel`
- Use **plural names** for arrays → `users`, `colors`
- Use meaningful names → `studentAge` ✅ (not `a`, `x`)
- Use `is`, `has`, `can` for booleans → `isValid`, `hasError`

## 📤 Output - Displaying Output in JavaScript

There are several ways to display output in JavaScript:

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Method</th>
    <th>Output Location</th>
    <th>Use Case</th>
    <th>Can Include HTML?</th>
  </tr>
  <tr>
    <td><strong>Console Logging</strong></td>
    <td>Browser Console (F12)</td>
    <td>Debugging, testing</td>
    <td>No (shows as text)</td>
  </tr>
  <tr>
    <td><strong>alert()</strong></td>
    <td>Pop-up dialog box</td>
    <td>Important messages</td>
    <td>No (shows as text)</td>
  </tr>
  <tr>
    <td><strong>document.write()</strong></td>
    <td>On the HTML page</td>
    <td>Quick output (old method)</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td><strong>DOM manipulation</strong></td>
    <td>Specific HTML element</td>
    <td>Modern apps (recommended)</td>
    <td>Yes</td>
  </tr>
</table>


### 1️⃣ Console Logging 

Display output in the **Browser Console** (F12 → Console tab)

```js
console.log(`Hello, ${name}! This is a message in the console.`);
console.warn("This is a warning message.");
console.error("This is an error message.");
```

**Best for:** Debugging, testing, development

---

### 2️⃣ `alert()` - Browser Pop-up

Display a **dialog box** that the user must close

```js
alert("Welcome to JavaScript!");
alert("Your score is: " + 100);
alert(`Hello, ${name}! This is a message in an alert box.`);
```

**Best for:** Important messages, user confirmations

---

### 3️⃣ `document.write()` - Write to HTML Page

Display output **directly on the page** (use before page loads)

```js
document.write("This content is written using document.write() method.");
document.write("<h3>This content is written using document.write()</h3>");
document.write("<p>Hello, " + name + "! This is a message in a document.write() method.</p>");
```

⚠️ **Warning**: Calling `document.write()` after page load (e.g., in a button click, `setTimeout()` function, or after `DOMContentLoaded`) **will replace the entire page content**.

---

### 4️⃣ DOM Manipulation - Insert Content into HTML Elements

Use DOM methods to insert content into specific HTML elements (most common in modern code).

#### 4️⃣.1️⃣ `textContent` - Insert Plain Text (Safe)

Gets or sets the **plain text** content of an element (no HTML tags will be rendered)

```js
// Inserts plain text (no HTML tags will be rendered)
document.getElementById("textContent").textContent = `Hello, ${name}! This is a message in textContent element.`;
```

**Best for:** Simple text updates, safe from code injection

---

#### 4️⃣.2️⃣ `innerHTML` - Insert HTML Content (Powerful)

Gets or sets the **HTML content** of an element (HTML tags will be rendered)

```js
// Inserts HTML content (HTML tags will be rendered)
document.getElementById("innerHTML").innerHTML = `Hello, <strong>${name}</strong>! This is a message in an innerHTML element.`;

// Appending more content using += operator
document.getElementById("innerHTML").innerHTML += "<p>This is additional content added using innerHTML.</p>";
```

**Best for:** Inserting formatted HTML, building dynamic pages

**⚠️ Security Warning**: Only use `innerHTML` with trusted content. Never use with untrusted user input!

---

#### 4️⃣.3️⃣ `createElement()` + `appendChild()` - Create New Elements (✅ Safest & Most Flexible)

Create new HTML elements dynamically and add them to the DOM

```js
// Create a new heading element
const newHeading = document.createElement("h2");
newHeading.textContent = `Hello, ${name}! This is a heading created using createElement()`;

// Add the heading to the page (as LAST CHILD)
document.getElementById("createElement").appendChild(newHeading);

// Create a new paragraph element
const newParagraph = document.createElement("p");
newParagraph.textContent = `Hello, ${name}! This is a paragraph created using createElement()`;

// Add the paragraph to the page (as LAST CHILD)
document.getElementById("createElement").appendChild(newParagraph);
```

**Best for:** Dynamically creating elements from scratch, building lists and tables

---

#### 4️⃣.4️⃣ `insertAdjacentHTML()` - Insert HTML at Specific Positions

Insert HTML at specific positions **relative to an element**. Has 4 position options:

``` html
<!-- HTML structure for demonstration -->
<!-- Visual representation: -->
<!-- beforebegin -->    ← OUTSIDE (above)
<div id="insertAdjacentHTML">
  <!-- afterbegin -->   ← INSIDE (at top)
  existing content
  <!-- beforeend -->    ← INSIDE (at bottom)
</div>
<!-- afterend -->       ← OUTSIDE (below)
```

```js
const element = document.getElementById("insertAdjacentHTML");

// Position 1: afterbegin - Insert INSIDE at the START
element.insertAdjacentHTML("afterbegin", "<p style='color: blue;'>→ afterbegin: Inserted INSIDE at the START</p>");

// Position 2: beforeend - Insert INSIDE at the END
element.insertAdjacentHTML("beforeend", "<p style='color: green;'>→ beforeend: Inserted INSIDE at the END</p>");

// Position 3: beforebegin - Insert OUTSIDE, BEFORE the element
element.insertAdjacentHTML("beforebegin", "<p style='color: red;'>→ beforebegin: Inserted OUTSIDE, BEFORE the element</p>");

// Position 4: afterend - Insert OUTSIDE, AFTER the element
element.insertAdjacentHTML("afterend", "<p style='color: purple;'>→ afterend: Inserted OUTSIDE, AFTER the element</p>");
```

---

### 📊 DOM Methods Comparison & Decision Guide

<table border="1" cellpadding="10" cellspacing="0">
  <tr>
    <th>Method</th>
    <th>What It Does</th>
    <th>Safety</th>
    <th>When to Use</th>
  </tr>
  <tr>
    <td><strong><code>textContent</code></strong></td>
    <td>Get/set plain text only (no HTML rendering)</td>
    <td>✅ Very Safe</td>
    <td>✓ Displaying simple text<br/>✓ Showing user input or external data<br/>✓ You don't need HTML formatting</td>
  </tr>
  <tr>
    <td><strong><code>innerHTML</code></strong></td>
    <td>Get/set HTML markup (renders HTML tags)</td>
    <td>⚠️ Trusted Only</td>
    <td>✓ Building HTML with formatting (bold, colors)<br/>✓ Content is from your own code<br/>✓ You need to insert multiple HTML elements</td>
  </tr>
  <tr>
    <td><strong><code>createElement()</code></strong></td>
    <td>Create new element (most control)</td>
    <td>✅ Safest</td>
    <td>✓ Creating elements dynamically<br/>✓ Building lists, tables, or complex structures<br/>✓ Maximum safety and control needed</td>
  </tr>
  <tr>
    <td><strong><code>insertAdjacentHTML()</code></strong></td>
    <td>Insert HTML at specific positions (4 options)</td>
    <td>⚠️ Trusted Only</td>
    <td>✓ You need precise positioning (before/after)<br/>✓ Adding sidebar content, headers, footers<br/>✓ HTML content is trusted and from your code</td>
  </tr>
</table>

---

## 📥 Input - Getting Input in JavaScript

There are several ways to get input from users:

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Method</th>
    <th>Input Type</th>
    <th>Returns</th>
    <th>Best For</th>
  </tr>
  <tr>
    <td><strong>prompt()</strong></td>
    <td>Simple text input</td>
    <td>String (or null)</td>
    <td>Quick input, simple scripts</td>
  </tr>
  <tr>
    <td><strong>input type="text"</strong></td>
    <td>Text</td>
    <td>String</td>
    <td>Modern web apps</td>
  </tr>
  <tr>
    <td><strong>input type="number"</strong></td>
    <td>Numbers</td>
    <td>String (convert with parseInt/parseFloat)</td>
    <td>Numeric input</td>
  </tr>
  <tr>
    <td><strong>input type="checkbox"</strong></td>
    <td>Yes/No</td>
    <td>Boolean (.checked)</td>
    <td>Multiple selections</td>
  </tr>
  <tr>
    <td><strong>input type="radio"</strong></td>
    <td>One option</td>
    <td>String (.value)</td>
    <td>Single selection</td>
  </tr>
  <tr>
    <td><strong>textarea</strong></td>
    <td>Multi-line text</td>
    <td>String</td>
    <td>Long text input</td>
  </tr>
  <tr>
    <td><strong>select</strong></td>
    <td>Dropdown menu</td>
    <td>String (.value)</td>
    <td>Choose from list</td>
  </tr>
</table>


### 1️⃣ `prompt()` - Simple Pop-up Input

Display a **dialog box** where the user can type

```js
let name = prompt("What is your name?");
console.log(name);  // Displays user's input

let age = prompt("How old are you?", "18");  // Default value: "18"
console.log(age);   // User input or default

// Handling cancellation
let userInput = prompt("Enter your favorite color:");
if (userInput === null) {
  console.log("User cancelled the prompt");
} else {
  console.log("Your favorite color is: " + userInput);
}
```

**Returns:** String (or `null` if user cancels)

### 2️⃣ HTML Input Fields - Best for Modern Web

Create input fields in HTML and get values with JavaScript

**HTML:**
```html
<input type="text" id="nameInput" placeholder="Enter your name">
<input type="number" id="ageInput" placeholder="Enter your age">
<button id="submitBtn">Submit</button>
<div id="result"></div>
```

**JavaScript:**
```js
// Get the input value
let name = document.getElementById("nameInput").value;
let age = document.getElementById("ageInput").value;

// Handle button click
document.getElementById("submitBtn").addEventListener("click", function() {
  let inputValue = document.getElementById("nameInput").value;
  console.log("You entered: " + inputValue);
});
```

### 3️⃣ Different Input Types

```html
<!-- Text input -->
<input type="text" id="username" placeholder="Username">

<!-- Password input -->
<input type="password" id="password" placeholder="Password">

<!-- Email input -->
<input type="email" id="email" placeholder="Email">

<!-- Number input -->
<input type="number" id="age" placeholder="Age">

<!-- Checkbox -->
<input type="checkbox" id="agree"> I agree

<!-- Radio buttons -->
<input type="radio" name="gender" value="male"> Male
<input type="radio" name="gender" value="female"> Female

<!-- Dropdown/Select -->
<select id="country">
  <option value="">Select Country</option>
  <option value="usa">USA</option>
  <option value="uk">UK</option>
</select>

<!-- Text area (multi-line) -->
<textarea id="comments" rows="4" cols="50"></textarea>
```

**Get values:**
```js
// Text, email, password
let username = document.getElementById("username").value;

// Checkbox (true/false)
let isAgreed = document.getElementById("agree").checked;

// Radio button
let gender = document.querySelector('input[name="gender"]:checked').value;

// Dropdown
let country = document.getElementById("country").value;

// Text area
let comments = document.getElementById("comments").value;
```


### 🎯 Practical Example - Input + Output

```html
<input type="text" id="userName" placeholder="Enter your name">
<input type="number" id="userAge" placeholder="Enter your age">
<button id="submitBtn">Submit</button>
<div id="output"></div>
```

```js
document.getElementById("submitBtn").addEventListener("click", function() {
  // Get input values
  let name = document.getElementById("userName").value;
  let age = document.getElementById("userAge").value;
  
  // Validate input
  if (name === "" || age === "") {
    alert("Please fill in all fields!");
    return;
  }
  
  // Display output
  let result = `Hello ${name}! You are ${age} years old.`;
  document.getElementById("output").textContent = result;
  
  // Also log to console
  console.log(result);
});
```

---


---

## 🧮 Arithmetic Operators

Arithmetic operators perform mathematical calculations on numbers.

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Operator</th>
    <th>Name</th>
    <th>Example</th>
    <th>Result</th>
  </tr>
  <tr>
    <td><strong>+</strong></td>
    <td>Addition</td>
    <td><code>5 + 3</code></td>
    <td><code>8</code></td>
  </tr>
  <tr>
    <td><strong>-</strong></td>
    <td>Subtraction</td>
    <td><code>5 - 3</code></td>
    <td><code>2</code></td>
  </tr>
  <tr>
    <td><strong>*</strong></td>
    <td>Multiplication</td>
    <td><code>5 * 3</code></td>
    <td><code>15</code></td>
  </tr>
  <tr>
    <td><strong>/</strong></td>
    <td>Division</td>
    <td><code>15 / 3</code></td>
    <td><code>5</code></td>
  </tr>
  <tr>
    <td><strong>%</strong></td>
    <td>Modulus (remainder)</td>
    <td><code>17 % 5</code></td>
    <td><code>2</code></td>
  </tr>
  <tr>
    <td><strong>**</strong></td>
    <td>Exponentiation (power)</td>
    <td><code>2 ** 3</code></td>
    <td><code>8</code></td>
  </tr>
</table>

### 💡 Examples

```js
let a = 10;
let b = 3;

console.log(a + b);      // 13 (addition)
console.log(a - b);      // 7  (subtraction)
console.log(a * b);      // 30 (multiplication)
console.log(a / b);      // 3.333... (division)
console.log(a % b);      // 1  (remainder: 10 ÷ 3 = 3 remainder 1)
console.log(a ** b);     // 1000 (exponentiation: 10 to the power of 3)
```

### 🎯 Assignment Operators (Shorthand)

```js
let x = 10;

x += 5;   // x = x + 5;  → 15
x -= 3;   // x = x - 3;  → 12
x *= 2;   // x = x * 2;  → 24
x /= 4;   // x = x / 4;  → 6
x %= 3;   // x = x % 3;  → 0
```

### 🎯 Increment & Decrement

```js
let count = 5;

count++;   // 6 (increment by 1)
count--;   // 5 (decrement by 1)

console.log(++count);  // 6 (pre-increment, then log)
console.log(count++);  // 6 (log, then increment)
```

### ⚠️ Order of Operations (PEMDAS)

```js
let result = 2 + 3 * 4;    // 14 (multiplication first)
let result2 = (2 + 3) * 4; // 20 (parentheses first)
```

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