# JavaScript Fundamentals

## Introduction to JavaScript

- JavaScript is a versatile scripting language used for web development
- Can be embedded directly in HTML documents or included in separate files
- Executes on the client side (browser) and server side (Node.js)

## Basic JavaScript Concepts

### Variables
- `var`: Function-scoped variable (older, generally avoided)
- `let`: Block-scoped variable (recommended for most cases)
- `const`: Block-scoped constant (use when value won't change)

### Data Types
- **Primitives**: String, Number, Boolean, Null, Undefined, Symbol
- **Complex**: Object, Array, Function

### Operators
- Arithmetic: `+`, `-`, `*`, `/`, `%`, `**`
- Comparison: `==`, `===`, `!=`, `!==`, `<`, `>`, `<=`, `>=`
- Logical: `&&`, `||`, `!`
- Assignment: `=`, `+=`, `-=`, `*=`, `/=`

## Control Flow

### Conditionals
- `if` statements
- `else if` statements
- `else` statements
- Ternary operator: `condition ? true : false`
- `switch` statements with `case` and `break`

### Loops
- `for` loop: `for(let i = 0; i < length; i++)`
- `while` loop
- `do...while` loop
- `for...in` loop (iterates over object keys)
- `for...of` loop (iterates over array values)
- `forEach()` method

## Functions

### Declaration and Invocation
- Function declaration: `function name() {}`
- Function expression: `const name = function() {}`
- Arrow functions: `const name = () => {}`
- Immediately Invoked Function Expression (IIFE): `(function() {})()`

### Parameters and Arguments
- Parameters are placeholders in function definition
- Arguments are actual values passed to the function
- Default parameters: `function(param = default value)`
- Rest parameters: `function(...args)`

### Return Values
- Functions can return values with `return` keyword
- If no return statement, function returns `undefined`

## Objects and Arrays

### Objects
- Created with `{}` or `new Object()`
- Contains key-value pairs (properties and methods)
- Access properties with dot notation: `obj.property`
- Access properties with bracket notation: `obj['property']`
- Add/modify properties dynamically

### Arrays
- Created with `[]` or `new Array()`
- Zero-indexed collections of values
- Common methods: `push()`, `pop()`, `shift()`, `unshift()`, `slice()`, `splice()`, `map()`, `filter()`, `reduce()`, `forEach()`, `find()`, `findIndex()`, `includes()`, `indexOf()`, `join()`, `reverse()`, `sort()`

## Scope

### Variable Scope
- **Global scope**: Variables accessible everywhere
- **Function scope**: Variables accessible within the function
- **Block scope**: Variables accessible within the block (let and const)
- **Lexical scope**: Inner functions can access outer function variables

### Closures
- Functions that have access to variables in their outer (enclosing) function's scope
- Allows for data privacy and creating private variables

## The DOM

### Document Object Model
- Tree-like structure representing HTML elements
- JavaScript can manipulate DOM to change page content
- Access elements: `getElementById()`, `querySelector()`, `querySelectorAll()`, `getElementsByClassName()`, `getElementsByTagName()`
- Modify content: `innerHTML`, `textContent`, `setAttribute()`, `classList.add()`, `classList.remove()`, `classList.toggle()`

### Events
- User interactions trigger events (click, submit, mouseover, etc.)
- Event listeners: `addEventListener('event', callback)`
- Event object contains information about the event
- Event bubbling: Events propagate up the DOM tree
- Event capturing: Events propagate down the DOM tree
- Prevent default behavior: `event.preventDefault()`

## Asynchronous JavaScript

### Callbacks
- Functions passed as arguments to be executed later
- Used for handling asynchronous operations
- Callback hell/pyramid of doom when nested

### Promises
- Represents eventual completion (or failure) of async operation
- States: Pending, Fulfilled, Rejected
- Methods: `.then()`, `.catch()`, `.finally()`
- `Promise.all()`, `Promise.race()`, `Promise.any()`

### Async/Await
- Syntactic sugar for working with Promises
- `async` keyword marks function as asynchronous
- `await` keyword pauses execution until Promise resolves
- Makes asynchronous code look synchronous and more readable
- Error handling with `try...catch`

## Error Handling

### Try-Catch
- `try` block contains code that might throw an error
- `catch` block handles the error
- `finally` block executes regardless of outcome
- `throw` keyword to create custom errors

### Error Types
- `Error`: Generic error
- `TypeError`: Wrong type of value
- `ReferenceError`: Variable not defined
- `SyntaxError`: Invalid code syntax
- `RangeError`: Value outside acceptable range

## Working with APIs

### Fetch API
- Modern way to make HTTP requests
- Returns a Promise
- Syntax: `fetch(url).then(response => response.json()).then(data => console.log(data))`
- Can use `async/await` for cleaner code

### JSON
- JavaScript Object Notation
- Text format for data exchange
- Methods: `JSON.stringify()` converts object to string, `JSON.parse()` converts string to object

## ES6+ Features

### Let and Const
- `let`: Block-scoped, can be reassigned
- `const`: Block-scoped, cannot be reassigned
- Prefer `const` by default, use `let` when reassignment needed

### Template Literals
- Backtick syntax: `` `Hello ${name}` ``
- Allows variable interpolation and multi-line strings

### Destructuring
- Extract values from objects and arrays
- Object: `const {name, age} = person`
- Array: `const [first, second] = array`

### Spread Operator
- `...` syntax spreads iterable elements
- Array spread: `[...array1, ...array2]`
- Object spread: `{...obj1, ...obj2}`

### Arrow Functions
- Syntax: `const func = () => {}`
- Implicit return for single expressions: `const func = () => value`
- Don't have their own `this` context

### Classes
- Syntax: `class ClassName {}`
- Constructor method: `constructor() {}`
- Methods defined in class
- Inheritance with `extends` keyword
- `super` keyword to call parent class methods

### Modules
- `import` keyword to import modules
- `export` keyword to export modules
- Default exports and named exports
- Helps organize code into reusable pieces

## Comparison Table (this picture!)

| Operator | Equality | Inequality | Strict Equal | Strict Unequal |
|----------|----------|-----------|---------|---------|
| Symbol | `==` | `!=` | `===` | `!==` |
| Loose/Flexible | Yes | Yes | No | No |
| Strict | No | No | Yes | Yes |
| Type Coercion | Yes | Yes | No | No |
| Performance | Slower | Slower | Faster | Faster |
| Use Case | Rarely | Rarely | Most cases | Most cases |

## Best Practices

1. Use `const` by default, `let` when needed, avoid `var`
2. Use meaningful variable and function names
3. Keep functions small and focused (Single Responsibility Principle)
4. Use async/await instead of callbacks
5. Handle errors properly with try-catch
6. Write DRY (Don't Repeat Yourself) code
7. Comment complex logic
8. Use linters and formatters
9. Test your code
10. Avoid global variables

## Common Pitfalls

- Confusing `==` with `===` (use `===`)
- Forgetting that `this` context changes in arrow functions vs regular functions
- Not handling Promise rejections
- Variable hoisting confusion with `var`
- Mutating objects/arrays unintentionally
- Not understanding closure
- Forgetting to bind methods in classes

## State Management Models

State management is crucial for handling shared application state across components.

### Why State Management is Needed

Modern apps require shared state for:
- **User info**: Authentication and user data
- **Theme**: Application appearance settings
- **Cart**: E-commerce shopping cart
- **Auth**: Authentication tokens and permissions
- **Server data**: Data fetched from backend
- **Coordination**: Synchronizing state across components

### Problems Without a State System

- **Prop drilling**: Passing props through multiple component levels
- **Unclear data flow**: Hard to track where state changes originate
- **Hard to debug updates**: Difficult to trace state changes
- **Unpredictable UI**: UI behavior becomes inconsistent

### Redux (A Statement Management Model)

A centralized state container with strict rules about how state changes:

#### Follows:
- **Single source of truth**: One centralized state object
- **State is immutable**: State cannot be directly modified
- **Changes are explicit**: All changes documented
- **Pure function update state**: Reducers are pure functions
  - UI → `dispatch(action)` → `reducer(state, action)` → `newState` → UI re-renders

#### Cons:
- **Boiler plate**: Requires lots of setup code
- **Verbose**: More code to write
- **Overkill for small apps**: Too much for simple applications

#### When to Use Redux:
- **Large apps**: Complex state management needed
- **Many devs**: Team coordination easier
- **Business rules matter**: Complex application logic
- **Auditability required**: Need to track all state changes

### Zustand

Lightweight global store using hooks and reference comparison.

#### Features:
- Lightweight global store using hooks and reference comparison
- Less rules, more freedom
- Follows:
  - **State is global**: Accessible anywhere
  - **Updates trigger re-renders via shallow reference checks**: Efficient updates
  - **You control structure**: Define your own patterns

#### Pros:
- **Minimal API**: Simple to learn and use
- **No reducers**: No action types needed
- **No action types**: Simpler mental model
- **Easy mental model**: Straightforward concepts

#### Cons:
- **Easier to accidentally mutate**: Less structure can lead to mistakes
- **Less structured**: Freedom can lead to poor organization
- **Harder to audit at scale**: Difficult to track changes as app grows

#### When to Use Zustand:
- **Small to medium apps**: Perfect for simpler applications
- **Rapid development**: Get started quickly
- **UI-centric state**: Better for component state
- **Replacing React context**: Lightweight alternative to Context API

### Signals

Reactive variables that track reads and writes automatically.

#### Features:
- Reactive variables that track reads and writes automatically
- They update only what uses the value
- Reads are tracked
- Writes trigger updates
- No reference equality needed
- Make re-renders precise

#### When to Use Signals:
- **Performance critical UI**: Highly optimized rendering needed
- **Large lists**: Efficiently render large datasets
- **Highly reactive systems**: Fine-grained reactivity required
- **Fine-grained updates**: Precise control over what re-renders

### Comparison Table (Big Picture)

| Feature | Redux | Zustand | Signals |
|---------|-------|---------|---------|
| State location | Global | Global | Distributed |
| Updates | Immutable | Immutable-ish | Mutable |
| Re-render granularity | Component | Component | Value-level |
| Boilerplate | High | Low | Low |
| Predictability | Very high | Medium | Medium |
| Learning curve | Steep | Easy | New mental model |

## Array/Object Methods

### Map → Transforms
Transforms each element in an array.

```javascript
const nums = [1, 2, 3];
const doubled = nums.map(n => n * 2);
```

### Filter → Remove
Filters array based on condition.

```javascript
const even = nums.filter(n => n % 2 === 0);
```

### Reduce → Accumulate
Accumulates values to a single result.

```javascript
const sum = nums.reduce((total, n) => total + n, 0);
```

### Purpose:
- **Declarative code**: Express intent clearly
- **Less mutation**: Avoid modifying original data
- **Cleaner logic**: More readable and maintainable
- **Easier testing**: Pure functions are easier to test

## Event Loop & Async Behavior

### JavaScript Execution Model

#### Single-Threaded Execution
- JavaScript is single-threaded, not blocking
- Single threaded means one call stack one thing executing at a time
- **Blocking**: Occupying the call stack so nothing else can run
  - **Blocking functions**:
    - While loops
    - For loops
  - **Effects** of blocking:
    - If stack is blocked UI can't repaint
    - Clicks don't respond
    - Promises don't resolve
    - Timers don't fire

#### Why Async Doesn't Block
- **Fetch data starts**: Initiates background request
- **Function pauses**: Stack clears
- **Stack clears**: Other code runs
- **Other is runs**: Page continues responding
- **Promise resolves**: then() function goes to microtask queue
- **Function resumes as a microtask**: Continues after stack is empty

### Async Behavior

#### Call Stack Syncs First
- Synchronous code executes first
- Background work sets the time out (web api) and fetches something which is network thread
- **Promises resolves**:
  - Resolves fetch
  - Then() function goes to microtask queue

#### Event Loop Order
- **Stack is empty**: Start processing
- **Run all micro tasks**: Execute microtask queue
- **Run one macro task**: Execute one task from task queue
- **Repeat**: Continue the cycle

### Different Calls

#### Different Queues:
- **Call stack**: Where functions execute
  - Is only controls call stack
- **Web api**: Timers, fetch, DOM
- **Task queue**: Set time out
- **Microtask queue**: Queue microtask
- **Event loop-traffic controller**: Can't run until the call stack is empty

#### Priority:
- **Synchronous code runs first**: All sync code executes
- **Promises go to microtask queue**: Prioritized before tasks
- **Set time out goes to task queue**: Lower priority
- **Microtask run before tasks**: Executed first

#### Micro task vs Macro task

##### Micro task
- **Promise.then()**
- **Async/await**
- **Queuemicrotask()**

##### Macro task
- **Set time out**
- **Set interval**
- **DOM events**
- **Message channel**

### Benefits:

- **Knowing this will help with race conditions**: Understand timing issues
- **Why await feels synchronous**: Stack clears, other runs, microtask queue prioritized
- **React rendering quirks**: Understand when components update
- **Animation and performance**: Optimize animations and rendering

### Summary

- **Single-threaded**: JS runs one thing at a time on one call stack.
- **Blocking**: Anything that prevents the call stack from clearing.
- **Event loop**: Moves queued work onto the stack when it's empty.
- **Async**: Work delegated to the environment, resumed later.
