        # JavaScript Fundamentals

        ## Closures
        A function that remembers variables from where it was created—even after that outer function finishes. Think of it as a function with a backpack of memory.

        **Benefits:**
        - React hooks use closures for further interaction
        - Event handlers
        - State isolation
        - Debounce/throttle (remembers timer, controls execution timing, prevents UI spam)
        - Private variables
        - Preserve state over time
        - Avoid global variables
        - Create isolated logic instances

        **How JS does encapsulation without classes:** Encapsulation is controlled access since it can only be called from JS.

        **Uses:**
        - Counters with multiple states
        - Controlled access for deposits
        - Safer async code
        - Cleaner API

        ---

        ## Event Loop & Async Behavior

        **Single-threaded, non-blocking:**
        - One call stack; one thing executing at a time
        - Blocking = occupying the call stack, preventing other code from running
        - Blocking functions: `while(true)`, for loops
        - Effects of blocking: UI can't repaint, clicks don't respond, promises don't resolve, timers don't fire
        - Why async doesn't block: fetch starts → function pauses → stack clears → other JS runs → promise resolves → function resumes as a microtask

        **Async behavior flow:**
        1. Call stack syncs first
        2. Background work (Web API) handles timers and fetches (network thread)
        3. Promise resolves, then() goes to microtask queue
        4. Event loop order: empty stack → run all microtasks → run one macrotask → repeat

        **Different execution contexts:**
        - **Call stack:** Where functions execute (JS controls only this)
        - **Web API:** Timers, fetch, DOM
        - **Task queue:** setTimeout callbacks
        - **Microtask queue:** Promise callbacks, queueMicrotask
        - **Event loop:** Traffic controller; can't run until call stack is empty

        **Priority:**
        1. Synchronous code runs first
        2. Promises → microtask queue
        3. setTimeout → task queue
        4. Microtasks run before tasks

        **Microtask vs Macrotask:**
        - **Microtasks:** Promise.then, async/await, queueMicrotask
        - **Macrotasks:** setTimeout, setInterval, DOM events, MessageChannel

        **Benefits of understanding this:**
        - Helps with race conditions
        - Explains why await feels synchronous
        - Clarifies React rendering quirks
        - Improves animation and performance

        ---

        ## Promises vs Async/Await

        **Important:** Async/await is NOT more powerful—it's just cleaner syntax for promises. Async/await uses promises + microtask queue. Async does NOT block JS; it only pauses that function.

        **Note:** You only wait for what you explicitly await.

        **When to use:**
        - **Application logic:** async/await
        - **Utility/library code:** Raw promises

        **Parallel async:**
        - Two sequential awaits = fetchA + wait + fetchB + wait
        - Better approach: Store in variables or use `Promise.all()` to start both immediately

        **Why it matters:**
        - Error handling
        - Sequential vs parallel async work
        - Readability in complex flows

        ---

        ## This, Prototypes, Classes

        **Lexical scope:** Determined by where code is written (const, let, closures, arrow function this).

        **`this` is NOT lexical:** It depends on how a function is called, not where it's defined. Set at call time, not definition time.

        **Prototypes:**
        Every JS object has a hidden link. Prototypes ARE classes in JS.

        ```javascript
        const animal = { eats: true };
        const dog = Object.create(animal);
        dog.barks = true;
        dog.eats; // true (found via prototype)
        ```

        **Use regular functions when:**
        - You need dynamic `this`
        - Writing methods or classes
        - Working with class components

        **Use arrow functions when:**
        - Callbacks
        - Event handlers
        - Preserving `this`
        - Functional utilities

        **Why it matters:**
        - Memory efficiency
        - Inheritance
        - Understanding React class components
        - Debugging `this` bugs

        ---

        ## Immutability & Reference vs Value

        **Value types** retain their value. **Reference types** change when other variables modify them.

        **Purpose:**
        - React re-renders
        - Redux, Zustand, signals
        - Debugging why it didn't update
        - Mutation causes silent bugs

        **Value vs Reference:**
        - **Values:** String, Number, Boolean, Null, Undefined, Symbol, BigInt
        - **References:** Object, Array, Function, Date, Map, Set

        **React re-rendering:**
        React does NOT deep compare state. To trigger a re-render, you must set state.

        **State management models:**

        | Model | Use Case | Pros | Cons |
        |-------|----------|------|------|
        | **Redux** | Large apps, many devs, strict rules needed | Single source of truth, immutable, explicit changes | Boilerplate, verbose, overkill for small apps |
        | **Zustand** | Small-medium apps, rapid development | Minimal API, no reducers, easy mental model | Easier to accidentally mutate, less structured |
        | **Signals** | Performance-critical UI, fine-grained updates | Automatic tracking, precise re-renders | Framework-dependent |

        ---

        ## Array/Object Methods

        **Map** → Transforms:
        ```javascript
        const nums = [1, 2, 3];
        const doubled = nums.map(n => n * 2);
        ```

        **Filter** → Removes:
        ```javascript
        const even = nums.filter(n => n % 2 === 0);
        ```

        **Reduce** → Accumulates:
        ```javascript
        const sum = nums.reduce((total, n) => total + n, 0);
        ```

        **Benefits:**
        - Declarative code
        - Less mutation
        - Cleaner logic
        - Easier testing

        ---

        ## How It All Ties Together

        - **Closures** → State & hooks
        - **Event loop** → Rendering & async bugs
        - **Promises** → Data flows
        - **Immutability** → UI consistency
        - **Prototypes** → Component behavior
        - **Array methods** → UI transformations

