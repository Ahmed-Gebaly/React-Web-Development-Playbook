
• React: open-source JS library for building UIs, mainly used for SPAs and mobile apps, best for small to medium-sized web applications.
• Developed by Facebook/meta, widely used for web apps.
• Components: reusable, nestable building blocks; defined as classes (old/OOP) or functions (modern/functional) returning JSX.
• JSX: HTML-like syntax in JS to describe UI structure in components.
• Props: read-only data passed from parent components to child components, customizes components.
• State: component-managed data, updated with setState(), triggers re-render.
• Virtual DOM: React updates a virtual DOM, then syncs minimal changes to real DOM for efficiency.
• Lifecycle methods: componentDidMount, componentDidUpdate, componentWillUnmount, etc.
• Hooks: useState, useEffect, useContext, etc., enable state and features in functional components.
• Integrates with Redux (state management), React Router (routing), and other libraries.

node install
npm create vite@latest my-react-app

npm create vite@latest my-react-app -- --template react
npm install
npm run dev

vite: a build tool that provides a faster and leaner development experience for modern web projects, supports React, Vue, and more.

React Compiler: Babel is commonly used to compile JSX and modern JavaScript features into compatible code for browsers. It transforms JSX syntax into React.createElement calls and converts ES6+ code into ES5 for broader browser support.
SWC: a super-fast JavaScript/TypeScript compiler written in Rust, can be used as an alternative to Babel for compiling React code, offering improved performance and faster build times.

main component file: src/App.jsx
```jsx
import React from 'react';
function App() {
  return (
    <div>
      <h1>Hello, React!</h1>
    </div>
  );
}

export default App;
```

---

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

