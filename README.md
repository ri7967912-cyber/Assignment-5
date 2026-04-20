# GitHub Issues Tracker

A web application to track and manage project issues, built with HTML, Tailwind CSS, DaisyUI, and vanilla JavaScript.

## Setup Instructions

1.  **Create a new folder** on your computer for the project.
2.  **Save the provided code** as `index.html` inside the folder you just created.
3.  **Open the `index.html` file** in your web browser to start using the application.

## Technology Stack

*   **HTML5**: Page structure.
*   **Tailwind CSS & DaisyUI**: Styling and UI components.
*   **JavaScript (Vanilla)**: All interactive functionality, including API calls, state management, and UI updates.
*   **Font Awesome**: For icons.

## Features

*   **Login Page**: Secure login with default credentials (`admin` / `admin123`).
*   **Dashboard**: View issues in a responsive 4-column grid layout.
*   **Filtering**: Tabs to filter issues by status (All, Open, Closed).
*   **Search**: Search for issues using keywords via the search bar.
*   **Issue Details**: Click on any issue card to open a modal with full details.
*   **Visual Cues**: Cards have a colored top border (green for Open, purple for Closed).
*   **Loading State**: A loading spinner is displayed while data is being fetched.

## API Integration

The application interacts with the provided REST API endpoints:

*   `GET /api/v1/lab/issues` - Fetch all issues
*   `GET /api/v1/lab/issue/{id}` - Fetch a single issue by ID
*   `GET /api/v1/lab/issues/search?q={searchText}` - Search for issues

---

## Questions & Answers (JavaScript Concepts)

### 1️⃣ What is the difference between var, let, and const?

`var`, `let`, and `const` are used to declare variables in JavaScript.

*   **`var`**:
    *   Function-scoped. A variable declared with `var` is available throughout the function in which it is defined.
    *   Can be re-declared and updated.
    *   Hoisted to the top of its scope but initialized as `undefined`.
*   **`let`**:
    *   Block-scoped (`{}`). It is only available within the block it was created.
    *   Can be updated but **cannot be re-declared** within the same scope.
    *   Hoisted but not initialized, resulting in a `ReferenceError` if accessed before declaration.
*   **`const`**:
    *   Block-scoped like `let`.
    *   Must be initialized during declaration.
    *   **Cannot be updated or re-declared**. For objects and arrays, the properties can be changed, but the variable itself cannot be reassigned.

### 2️⃣ What is the spread operator (...)?

The spread operator (`...`) allows an iterable (like an array, string, or object) to be expanded into individual elements.

*   **Arrays**: `const newArray = [...oldArray, 4, 5];` (combines arrays)
*   **Objects**: `const newObject = { ...oldObject, newProp: 'value' };` (shallow copies or merges objects)
*   **Function calls**: `const numbers = [1, 2, 3]; Math.max(...numbers);` (spreads array elements as arguments)

### 3️⃣ What is the difference between map(), filter(), and forEach()?

All three are array methods that iterate over elements, but they serve different purposes:

*   **`map()`**:
    *   Creates a **new array** populated with the results of calling a function on every element.
    *   Used for transforming data.
    *   Example: `const squares = [1, 2, 3].map(x => x * x); // [1, 4, 9]`
*   **`filter()`**:
    *   Creates a **new array** with elements that pass a test defined by a provided function.
    *   Used for selecting a subset of data.
    *   Example: `const evens = [1, 2, 3, 4].filter(x => x % 2 === 0); // [2, 4]`
*   **`forEach()`**:
    *   Executes a provided function once for each array element.
    *   **Does not return a new array**; returns `undefined`.
    *   Used for performing side effects (e.g., logging, updating external variables).
    *   Example: `[1, 2, 3].forEach(x => console.log(x));`

### 4️⃣ What is an arrow function?

An arrow function is a shorter syntax for writing function expressions. It was introduced in ES6.

*   **Syntax**: `(param1, param2) => { return expression; }`
*   **Key Feature**: It does not have its own `this` context. Instead, it inherits `this` from the surrounding (lexical) scope. This is different from regular functions, which have their own `this`.
*   **Use Case**: Excellent for short callbacks and when you need to preserve the `this` value from the enclosing context.

### 5️⃣ What are template literals?

Template literals are string literals that allow embedded expressions and multi-line strings. They are enclosed by backticks (`` ` ``) instead of quotes.

*   **Embedded Expressions**: `${expression}`.
*   **Multi-line Strings**: Strings can span multiple lines without needing `\n` or concatenation.
*   **Example**: 
    ```javascript
    const name = 'World';
    console.log(`Hello, ${name}!`); // Output: Hello, World!
    
    const multiLine = `
      This is
      a multi-line
      string.
    `;