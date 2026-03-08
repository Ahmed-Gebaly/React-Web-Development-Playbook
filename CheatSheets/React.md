# React Cheat Sheet

> **React** is an open-source JavaScript library for building user interfaces, mainly used for single-page applications (SPAs) and mobile apps. It is best suited for small to medium-sized web applications.

## Key Features
- **Developed by:** Facebook/Meta, widely used for web apps.
- **Components:** Reusable, nestable building blocks. Defined as classes (old/OOP) or functions (modern/functional) that return JSX.
- **JSX:** HTML-like syntax in JavaScript to describe UI structure in components.
- **Props:** Read-only data passed from parent to child components to customize them.
- **State:** Data managed within a component, updated with `setState()` (class) or hooks (function), triggers re-render.
- **Virtual DOM:** React updates a virtual DOM, then syncs minimal changes to the real DOM for efficiency.
- **Lifecycle Methods:** `componentDidMount`, `componentDidUpdate`, `componentWillUnmount`, etc. (class components).
- **Hooks:** `useState`, `useEffect`, `useContext`, etc., enable state and features in functional components.
- **Ecosystem:** Integrates with Redux (state management), React Router (routing), and other libraries.

## Quick Installation Steps
1. **Install Node.js** from [nodejs.org](https://nodejs.org/)
2. **Create React app with Vite:**
  ```bash
  npm create vite@latest my-react-app -- --template react
  cd my-react-app
  npm install
  npm run dev
  ```
3. Open the local URL (usually http://localhost:5173) in your browser.


## Vite: Modern React Build Tool

- Super-fast dev server and builds
- Instant hot reload (HMR)
- Simple config, works out-of-the-box
- Supports React, Vue, Svelte, and more
- Replaces Create React App (CRA) for new projects


## React Compilers: Babel & SWC

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

## React Component
Components are the building blocks of a React application. 

### Simple Example: Call a component from another file (About)

This example shows how to create a simple About component in a separate file and use it inside the return of the App component.

#### File: src/about.jsx
```jsx
// src/about.jsx
import React from 'react';

export function About() {
  return (
    <section>
      <h2>About Us</h2>
      <p>This is a simple About section in React.</p>
    </section>
  );
}
```
#### File: src/contact.jsx
```jsx
// src/contact.jsx
import React from 'react';

export function Contact() {
  return (
    <section>
      <h2>Contact Us</h2>
      <p>This is a simple Contact section in React.</p>
    </section>
  );
}
```
#### File: src/App.jsx
```jsx
// src/App.jsx
import React from 'react';
import { About } from './about'; // Import the About component
import { Contact } from './contact'; // Import the Contact component

function App() {
  return (
    <div>
      <h1>Welcome to My App</h1>
      {/* Call the About and Contact components inside the return of App */}
      <About />
      <Contact></Contact>
    </div>
  );
}

export default App;
```

**Key Points:**
- Define each component in its own file for clarity.
- Use JSX to describe the UI structure.
- Import and use components as JSX tags inside the return statement.


## React Props
Props are read-only data passed from a parent component to a child component. They enable you to:
- Customize and configure child components
- Make components reusable and dynamic
- Control component behavior
- Enable one-way data flow (parent → child)