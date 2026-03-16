# React Cheat Sheet

> **React** quick reference and best practices.

## 📄 Overview

React is an open-source JavaScript library for building user interfaces, mainly used for single-page applications (SPAs) and mobile apps. Best for small to medium-sized web applications, one way data flow, and component-based architecture.

## 🗂️ Key Features
- **Developed by:** Facebook/Meta, widely used for web apps
- **Components:** Reusable, nestable building blocks (class or function)
- **JSX:** HTML-like syntax in JavaScript
- **Props:** Read-only data passed from parent to child
- **State:** Data managed within a component, triggers re-render
- **Virtual DOM:** Efficient UI updates
- **Lifecycle Methods:** For class components
- **Hooks:** For functional components (`useState`, `useEffect`, ...)
- **Ecosystem:** Integrates with Redux, React Router, etc.

## 🏗️ Quick Installation

```bash
npm create vite@latest my-react-app -- --template react
cd my-react-app
npm install
npm run dev
```
Open http://localhost:5173 in your browser.

## ⚡ Vite: Modern React Build Tool
- Super-fast dev server and builds
- Instant hot reload (HMR)
- Simple config, works out-of-the-box
- Supports React, Vue, Svelte, and more
- Replaces Create React App (CRA)

## 🛠️ React Compilers: Babel & SWC
React uses compilers to turn JSX and modern JavaScript (ES6+) into browser-compatible code.
<table border="1" cellpadding="6" cellspacing="0">
  <tr>
    <th>Compiler</th>
    <th>Language</th>
    <th>Speed</th>
    <th>Features</th>
    <th>Usage</th>
  </tr>
  <tr>
    <td><b>Babel</b></td>
    <td>JS</td>
    <td>Medium</td>
    <td>Most common, highly configurable, big plugin ecosystem, transforms JSX/ES6+ to ES5</td>
    <td>Default for many tools</td>
  </tr>
  <tr>
    <td><b>SWC</b></td>
    <td>JS/TS</td>
    <td>Blazing</td>
    <td>Super-fast (Rust), drop-in for Babel, used by Vite/Next.js, compiles JS/TS</td>
    <td>Modern React setups</td>
  </tr>
</table>

## 🧱 React Component
Components are the building blocks of a React application. In modern React, components are written as functions (functional components).

### Structure of a Functional Component
```jsx
// 1. Define the component function (name must start with a capital letter)
function MyComponent() {
  return <h1>Hello, I am a component!</h1>;
}

// 2. Export the component (for use in other files)
export default MyComponent;
```

**Key Points:**
- Always start component names with a capital letter (e.g., `MyComponent`)
- The function must return JSX (looks like HTML, but is JavaScript)
---

### 🧩 Example: Using (Calling) a Component

You can use (call) a component by writing it as a JSX tag inside another component's return statement.

```jsx
// File: src/MyComponent.jsx
function MyComponent() {
  return <h2>This is MyComponent!</h2>;
}

export default MyComponent;
```

```jsx
// File: src/App.jsx
import MyComponent from './MyComponent';

function App() {
  return (
    <div>
      <h1>Welcome to My App</h1>
      {/* Call MyComponent inside App's return */}
      <MyComponent />
    </div>
  );
}

export default App;
```

**How it works:**
- `<MyComponent />` renders the MyComponent function and inserts its JSX output.
- You can reuse components as many times as needed.

## 🏷️ React Props
Props are read-only data passed from a parent component to a child component.

**Key Points:**
- Props let you customize and configure child components from the parent
- Make components reusable and dynamic by passing different values
- Control component behavior (e.g., show/hide, enable/disable, change text)
- Enforce one-way data flow (parent → child only)
- Props can be any JavaScript value: string, number, boolean, array, object, or function
- Use curly braces `{}` for non-string values (e.g., numbers, variables, expressions)
- Props are read-only in the child; only the parent can change them

**Disadvantages of Props:**
- Props are immutable, so child components cannot modify them
- Can lead to "prop drilling" if passed through many levels of components
- Overuse can make components less reusable and harder to maintain
- Can cause performance issues if large data is passed as props

---

### Example: Passing and Using Props

```jsx
// File: src/Greeting.jsx
function Greeting(props) {
  return <h2>Hello, {props.name}!</h2>;
}

export default Greeting;
```

```jsx
// File: src/App.jsx
import Greeting from './Greeting';

function App() {
  return (
    <div>
      <Greeting name="Sara" />
      <Greeting name="Ahmed" />
    </div>
  );
}

export default App;
```

In this example, the `Greeting` component receives a `name` prop and uses it to display a personalized greeting. The `App` component calls `Greeting` twice with different names, demonstrating how props can make components reusable and dynamic.


### Children Prop
The `children` prop is a special built-in prop in React that allows you to pass JSX elements, components, or even plain text between the opening and closing tags of a component. It enables you to:
- Create wrapper or layout components that can contain any content (flexible composition)
- Build reusable, generic components that work with arbitrary children
- Avoid hardcoding content inside a component, making it more flexible
- Passing dynamic content to a component without extra props

**Example:**
```jsx
// File: src/Children.jsx
function Container({ children }) {
  return (
    <div>
        {children}
        <p>This is a container component that can wrap any content.</p>
    </div>
  );
}
export default Container;
```

```jsx
// File: src/App.jsx
import Container from './Children';

function App() {
  return (
    <Container>
      <h1>Hello, World!</h1>
      <p>This is inside the container.</p>
    </Container>
  );
}
export default App;
```
In this example, the `Container` component uses the `children` prop to render whatever content is passed between its opening and closing tags. The `App` component wraps some JSX inside the `Container`, demonstrating how the `children` prop allows for flexible composition of components.

### Destructuring Props
Destructuring props in the function parameters makes code cleaner and more readable by directly accessing the needed properties.

```jsx
// Without Destructuring
function Contact(props) {
  return <h2>{props.username} - {props.email}</h2>;
}

// With Destructuring (Recommended)
function Contact({ username, email }) {
  return <h2>{username} - {email}</h2>;
}

// Usage
<Contact username="Sara" email="sara@example.com" />
```

---

### Props with Multiple Values
Pass multiple props to customize component behavior and data display.

```jsx
function NewContact(props) {
  return (
    <div>
      <h3>{props.name}</h3>
    </div>
  );
}

// Usage - Pass single or multiple props
<NewContact name="Ahmed" />
```

---

### Props with Expressions and Calculations
You can perform calculations or transformations directly within JSX using curly braces. Combine props with operators to compute values.

```jsx
function Cart({ title, price, stock }) {
  return (
    <div>
      <h3>{title}</h3>
      {/* Calculation: Add shipping cost to base price */}
      <p>Price (with $50 shipping): ${price + 50}</p>
      {/* Ternary operator for conditional values */}
      <p>Status: {stock ? "In Stock" : "Out of Stock"}</p>
    </div>
  );
}

// Usage
<Cart title="Laptop" price={1000} stock={true} />
// Output: Price (with $50 shipping): $1050
// Output: Status: In Stock
```

---

### Array Props and List Rendering
Pass arrays as props and render list items using `.map()`. Always provide a unique `key` prop for each rendered item.

```jsx
function UsersList({ users }) {
  return (
    <ul>
      {users.map((user, index) => (
        <li key={index}>
          {index} - {user.name} - {user.email}
        </li>
      ))}
    </ul>
  );
}

// Usage
const users = [
  { name: "Sara", email: "sara@example.com" },
  { name: "Ahmed", email: "ahmed@example.com" },
  { name: "Fatima", email: "fatima@example.com" }
];

<UsersList users={users} />
```

**Best Practice:** Use unique IDs as keys instead of array indices if the list can be reordered or items can be added/removed.

---

### Default Prop Values
Set default values for props so they have fallback values when not provided by the parent component.

```jsx
function Customer({ username = "Guest User" }) {
  return <h2>Hello {username}!</h2>;
}

// Usage 1: Without providing prop - uses default
<Customer />
// Output: Hello Guest User!

// Usage 2: With providing prop
<Customer username="Abdelmawgod" />
// Output: Hello Abdelmawgod!
```

---

### Children Prop
The `children` prop is a special built-in prop that allows you to pass JSX elements, components, or plain text between component tags. It enables flexible composition and wrapper components.

```jsx
// Wrapper component that can contain any content
function Wrapper({ children }) {
  return (
    <div style={{ border: "1px solid black", padding: "10px" }}>
      <h2>Wrapper Component</h2>
      <div>{children}</div>
      <p>This content is always visible inside the Wrapper.</p>
    </div>
  );
}

export default Wrapper;
```

```jsx
// Usage in parent component
<Wrapper>
  <h3>This is dynamic content</h3>
  <p>This can be anything passed between the tags</p>
</Wrapper>
```

---

### Render Props Pattern (Children as Function)
Pass a function as the `children` prop to allow components to receive data and control rendering. Advanced pattern for data sharing.

```jsx
function Data({ children }) {
  const data = {
    name: "Abdelmawgod",
    age: 30,
    city: "Cairo"
  };
  // children is a function that receives data
  return children(data);
}

export default Data;
```

```jsx
// Usage - children is a render function
<Data>
  {(data) => (
    <div>
      <p>Name: {data.name}</p>
      <p>Age: {data.age}</p>
      <p>City: {data.city}</p>
    </div>
  )}
</Data>
```

---

### Prop Drilling
Prop drilling occurs when you have to pass props through multiple levels of components that don't need them, just to get them to a deeply nested component. This can make code harder to maintain and understand.

**Solutions:**
- Use Context API or state management libraries (Redux, Zustand) to share data across the component tree without passing props manually
- Component composition and the `children` prop can reduce prop drilling by passing data directly to children

#### Fix prop drilling with children

**Before: Prop drilling (less ideal)**
```jsx
function App() {
  const user = { name: 'Sara', age: 30 };
  return <Parent user={user} />;
}

function Parent({ user }) {
  return <Child user={user} />;
}

function Child({ user }) {
  return <div>{user.name}</div>;
}
```

**After: Using children to avoid prop drilling (better)**
```jsx
function App() {
  const user = { name: 'Sara', age: 30 };
  return (
    <Parent>
      <Child user={user} />
    </Parent>
  );
}

function Parent({ children }) {
  return <div>{children}</div>;
}

function Child({ user }) {
  return <div>{user.name}</div>;
}
```

## React State


## Conditional rendering in React
Conditional rendering allows you to render different UI elements based on certain conditions. This is commonly done using JavaScript's conditional operators (like `if`, `&&`, `? :`) within the JSX.

### Conditional Rendering Methods
<table border="1" cellpadding="6" cellspacing="0">
  <tr>
    <th>Method</th>
    <th>Description</th>
    <th>Syntax Example</th>
  </tr>
  <tr>
    <td><code>if</code> statement</td>
    <td>Use outside JSX to set variables or return early</td>
    <td><code>if (condition) {'{ ... }'}</code></td>
  </tr>
  <tr>
    <td>Ternary (<code>? :</code>)</td>
    <td>Inline conditional, returns one of two values</td>
    <td><code>{'{condition ? <A /> : <B />}'}</code></td>
  </tr>
  <tr>
    <td>Logical AND (<code>&&</code>)</td>
    <td>Render if condition is true, nothing if false</td>
    <td><code>{'{condition && <A />}'}</code></td>
  </tr>
  <tr>
    <td><code>switch</code></td>
    <td>For multiple conditions, use outside JSX</td>
    <td><code>switch (value) {'{ case ... }'}</code></td>
  </tr>
</table>

#### Code Examples

**if statement (outside JSX):**
```jsx
function Example({ isLoggedIn }) {
  if (!isLoggedIn) {
    return <button>Login</button>;
  }
  return <h2>Welcome!</h2>;
}
```

**Ternary operator:**
```jsx
function Example({ isAdmin }) {
  return (
    <div>
      {isAdmin ? <h2>Admin Panel</h2> : <h2>User Panel</h2>}
    </div>
  );
}
```

**Logical AND (`&&`):**
```jsx
function Example({ showDetails }) {
  return (
    <div>
      <h2>Product</h2>
      {showDetails && <p>Details here...</p>}
    </div>
  );
}
```

**switch statement (outside JSX):**
```jsx
function StatusMessage({ status }) {
  let message;
  switch (status) {
    case 'loading':
      message = 'Loading...';
      break;
    case 'error':
      message = 'Error!';
      break;
    default:
      message = 'Ready!';
  }
  return <div>{message}</div>;
}
```