# JavaScript-Q-A
JavaScript Q&amp;A for recall the core and basic things for the interviews. 
R&D and Questions selection by : Tarak Siddhanta
==============================================================================
Here are short, conceptual answers with examples for each JavaScript question:

Sure! Here are conceptual explanations with brief examples for each question:

---

### 1. **Difference Between Call, Apply, and Bind**

- **`call`**: Invokes a function with a given `this` value and arguments provided one-by-one.
  ```javascript
  function greet(greeting) { console.log(greeting + ", " + this.name); }
  greet.call({ name: "Alice" }, "Hello"); // Output: Hello, Alice
  ```
- **`apply`**: Similar to `call`, but takes arguments as an array.
  ```javascript
  greet.apply({ name: "Bob" }, ["Hi"]); // Output: Hi, Bob
  ```
- **`bind`**: Returns a new function with a permanently bound `this` value and optional preset arguments.
  ```javascript
  const greetAlice = greet.bind({ name: "Alice" });
  greetAlice("Hey"); // Output: Hey, Alice
  ```

---

### 2. **Purpose of the Array `slice` Method**

- **`slice`**: Creates a new array with selected elements from an original array without modifying it.
  ```javascript
  const arr = [1, 2, 3, 4];
  const slicedArr = arr.slice(1, 3); // Output: [2, 3]
  ```

---

### 3. **Purpose of the Array `splice` Method**

- **`splice`**: Adds/removes elements in an array at specified indexes and modifies the original array.
  ```javascript
  const arr = [1, 2, 3, 4];
  arr.splice(1, 2, "a", "b"); // arr becomes [1, "a", "b", 4]
  ```

---

### 4. **Difference Between `slice` and `splice`**

- **`slice`**: Returns a new array; does not modify the original.
- **`splice`**: Modifies the original array and can add/remove elements.

---

### 5. **Difference Between `==` and `===` Operators**

- **`==`**: Checks for equality with type conversion.
  ```javascript
  "5" == 5; // true
  ```
- **`===`**: Strict equality; checks value and type.
  ```javascript
  "5" === 5; // false
  ```

---

### 6. **Lambda Expressions or Arrow Functions**

- Short syntax for defining functions; does not bind its own `this`.
  ```javascript
  const add = (a, b) => a + b;
  add(2, 3); // Output: 5
  ```

---

### 7. **First-Class Function**

- Functions are treated like any other variable.
  ```javascript
  const greet = () => "Hello";
  const sayHello = greet;
  sayHello(); // Output: Hello
  ```

---

### 8. **First-Order Function**

- A function that doesn’t accept functions as arguments or return a function.
  ```javascript
  const add = (a, b) => a + b;
  ```

---

### 9. **Difference Between First-Class and First-Order Functions**

- **First-Class**: Functions treated as values (e.g., stored in variables).
- **First-Order**: Functions that don’t take or return other functions.

---

### 10. **Higher-Order Function**

- Functions that take other functions as arguments or return functions.
  ```javascript
  const greet = (name) => () => "Hello, " + name;
  const sayHello = greet("Alice");
  sayHello(); // Output: Hello, Alice
  ```

---

### 11. **Unary Function**

- A function with one parameter.
  ```javascript
  const square = (x) => x * x;
  ```

---

### 12. **Currying Function**

- Transforms a function with multiple arguments into a series of unary functions.
  ```javascript
  const add = (a) => (b) => a + b;
  add(2)(3); // Output: 5
  ```

---

### 13. **Pure Function**

- A function with no side effects; returns the same output for given input.
  ```javascript
  const add = (a, b) => a + b; // Pure, as it only depends on a and b
  ```

---

### 14. **Difference Between `let` and `var`**

- **`var`**: Function-scoped, hoisted, allows redeclaration.
- **`let`**: Block-scoped, not hoisted, does not allow redeclaration within the same scope.

---

### 15. **Temporal Dead Zone (TDZ)**

- Period where a `let` or `const` variable is in scope but not yet declared, causing a `ReferenceError` if accessed.
  ```javascript
  console.log(x); // ReferenceError
  let x = 5;
  ```

---

### 16. **IIFE (Immediately Invoked Function Expression)**

- A function that executes immediately after creation.
  ```javascript
  (function() { console.log("Executed!"); })();
  ```

---

### 17. **Memoization**

- Caching results of function calls to optimize performance.
  ```javascript
  const memoize = (fn) => {
    const cache = {};
    return (x) => cache[x] || (cache[x] = fn(x));
  };
  ```

---

### 18. **Hoisting**

- JavaScript moves variable and function declarations to the top of their scope before execution.
  ```javascript
  console.log(x); // undefined
  var x = 5;
  ```

---

### 19. **Classes in ES6**

- Templates for creating objects; introduces syntactic sugar for constructor functions.
  ```javascript
  class Person {
    constructor(name) {
      this.name = name;
    }
  }
  ```

---

### 20. **Closures**

- Functions that capture the scope in which they were defined.
  ```javascript
  function outer() {
    let x = 10;
    return function inner() {
      console.log(x);
    };
  }
  ```

---

### 21. **Modules**

- JavaScript files that export code for reuse in other files, promoting encapsulation.
  ```javascript
  export const greet = () => "Hello";
  ```

---

### 22. **Scope in JavaScript**

- The current context of execution, defining accessible variables.
  - **Global Scope**: Variables accessible throughout the program.
  - **Local Scope**: Variables accessible within a function or block.

---

### 23. **Service Worker**

- Background script that helps manage offline caching, push notifications, and background sync for web applications.

---

### 24. **Promise**

- Represents a future value and handles asynchronous operations.
  ```javascript
  const promise = new Promise((resolve) => resolve("Done"));
  ```

---

### 25. **Callback Function**

- A function passed as an argument to another function, executed after the main function finishes.
  ```javascript
  function greet(callback) {
    callback();
  }
  ```

---

### 26. **`Promise.all`**

- Waits for multiple promises to resolve and returns an array of their results.
  A method that resolves when all promises in an array resolve or rejects if any promise rejects.
     Promise.all is a promise that takes an array of promises as an input (an iterable), and it gets resolved when all the promises get resolved or any one of them gets rejected. For example, the syntax of 
      promise.all method is below,
  
     Promise.all([Promise1, Promise2, Promise3])
     .then(result) => {   console.log(result) })
      .catch(error => console.log(`Error in promises ${error}`))

---

### 27. **Purpose of `Promise.race`**

- Returns the result of the first resolved/rejected promise in an array.
- Resolves or rejects as soon as the first promise in the array resolves or rejects.
     Promise.race() method will return the promise instance which is firstly resolved or rejected. Let's take an example of race() method where promise2 is resolved first
  ```javascript
  Promise.race([promise1, promise2]).then((result) => console.log(result));
  ```


### 28. ** What are the pros and cons of promises over callbacks
Below are the list of pros and cons of promises over callbacks,

**Pros:**

It avoids callback hell which is unreadable
Easy to write sequential asynchronous code with .then()
Easy to write parallel asynchronous code with Promise.all()
Solves some of the common problems of callbacks(call the callback too late, too early, many times and swallow errors/exceptions)

**Cons:**
It makes little complex code
You need to load a polyfill if ES6 is not supported

### 28. ** What is the purpose of void 0
Void(0) is used to prevent the page from refreshing. This will be helpful to eliminate the unwanted side-effect, because it will return the undefined primitive value. It is commonly used for HTML documents that use href="JavaScript:Void(0);" within an <a> element. i.e, when you click a link, the browser loads a new page or refreshes the same page. But this behavior will be prevented using this expression. For example, the below link notify the message without reloading the page

===========================================================================
Top 50 java script interview question for 2025 with conceptual answers based on "event" in java script with examples.
===========================================================================

Here's a list of top JavaScript interview questions centered around the concept of "events" with conceptual explanations and examples:

---

### 1. **What is an event in JavaScript?**
   - An **event** is an action or occurrence detected by the browser, such as user interactions (clicks, key presses) or changes (loading a page, resizing a window).
   ```javascript
   document.addEventListener('click', () => console.log('Clicked!'));
   ```

### 2. **How do you add an event listener to an element in JavaScript?**
   - Use `addEventListener`, specifying the event type and callback function.
   ```javascript
   button.addEventListener('click', () => alert('Button clicked!'));
   ```

### 3. **Difference between `onclick` attribute and `addEventListener`?**
   - `onclick` sets a single event handler, while `addEventListener` allows multiple handlers and event options.
   ```javascript
   button.onclick = () => console.log('Single handler');
   button.addEventListener('click', () => console.log('Multiple handlers allowed'));
   ```

### 4. **What is event bubbling?**
   - **Event bubbling** is when an event starts from the deepest target element and propagates upwards to ancestors.
   ```javascript
   // Clicking on child triggers event on both child and parent elements if not stopped
   ```

### 5. **What is event capturing?**
   - **Event capturing** (trickle down) is when an event starts from the root and propagates down to the target.
   ```javascript
   document.addEventListener('click', handler, true); // `true` enables capturing phase
   ```

### 6. **Difference between event bubbling and capturing?**
   - Bubbling: event goes up; Capturing: event goes down.

### 7. **How can you stop event propagation?**
   - Use `event.stopPropagation()` to prevent bubbling/capturing.
   ```javascript
   child.addEventListener('click', (e) => e.stopPropagation());
   ```

### 8. **What is `preventDefault()`?**
   - Prevents the default behavior of an event.
   ```javascript
   link.addEventListener('click', (e) => e.preventDefault());
   ```

### 9. **How to use `once` option in `addEventListener`?**
   - Set `{ once: true }` to automatically remove the event listener after its first invocation.
   ```javascript
   button.addEventListener('click', handler, { once: true });
   ```

### 10. **What is event delegation?**
   - Attaching a single event listener to a parent to manage events for multiple child elements.
   ```javascript
   list.addEventListener('click', (e) => {
     if (e.target.tagName === 'LI') console.log('List item clicked!');
   });
   ```

### 11. **How can you remove an event listener?**
   - Use `removeEventListener` with the same function reference.
   ```javascript
   button.removeEventListener('click', handler);
   ```

### 12. **What is the `event.target` property?**
   - Returns the element that triggered the event.
   ```javascript
   button.addEventListener('click', (e) => console.log(e.target));
   ```

### 13. **What is the `event.currentTarget` property?**
   - Refers to the element the event listener is attached to.
   ```javascript
   button.addEventListener('click', (e) => console.log(e.currentTarget));
   ```

### 14. **Difference between `event.target` and `event.currentTarget`?**
   - `target`: element that initiated event; `currentTarget`: element handling the event.

### 15. **What is `event.stopImmediatePropagation()`?**
   - Stops propagation and prevents other listeners on the same element from being called.

### 16. **How can you create a custom event?**
   - Use `CustomEvent` constructor.
   ```javascript
   const event = new CustomEvent('custom', { detail: { key: 'value' } });
   ```

### 17. **How to dispatch a custom event?**
   - Use `dispatchEvent` on the target element.
   ```javascript
   element.dispatchEvent(event);
   ```

### 18. **What is the `input` event?**
   - Fires when the value of an input changes.
   ```javascript
   input.addEventListener('input', (e) => console.log(e.target.value));
   ```

### 19. **What is the `change` event?**
   - Fires when an input element loses focus after its value changes.
   ```javascript
   input.addEventListener('change', (e) => console.log(e.target.value));
   ```

### 20. **Difference between `input` and `change` events?**
   - `input` fires immediately on value change; `change` fires on blur after change.

### 21. **What is a `focus` event?**
   - Fires when an element gains focus.
   ```javascript
   input.addEventListener('focus', () => console.log('Focused!'));
   ```

### 22. **What is a `blur` event?**
   - Fires when an element loses focus.
   ```javascript
   input.addEventListener('blur', () => console.log('Blurred!'));
   ```

### 23. **What is the `load` event?**
   - Fired when a page or resource finishes loading.
   ```javascript
   window.addEventListener('load', () => console.log('Page loaded!'));
   ```

### 24. **What is the `DOMContentLoaded` event?**
   - Fires when the DOM is fully loaded, before images and other resources.
   ```javascript
   document.addEventListener('DOMContentLoaded', () => console.log('DOM loaded!'));
   ```

### 25. **Difference between `load` and `DOMContentLoaded`?**
   - `load`: after all resources load; `DOMContentLoaded`: after the DOM is ready.

### 26. **What is the `resize` event?**
   - Fires when the window is resized.
   ```javascript
   window.addEventListener('resize', () => console.log('Window resized!'));
   ```

### 27. **What is the `scroll` event?**
   - Fires when an element is scrolled.
   ```javascript
   window.addEventListener('scroll', () => console.log('Scrolled!'));
   ```

### 28. **What is a `keyboard` event?**
   - Fires when a key is pressed (`keydown`, `keyup`, `keypress`).
   ```javascript
   document.addEventListener('keydown', (e) => console.log(e.key));
   ```

### 29. **What is a `mouseover` event?**
   - Fires when the pointer enters an element.
   ```javascript
   element.addEventListener('mouseover', () => console.log('Mouse over!'));
   ```

### 30. **What is a `mouseleave` event?**
   - Fires when the pointer leaves an element.
   ```javascript
   element.addEventListener('mouseleave', () => console.log('Mouse left!'));
   ```

### 31. **What is throttling and when would you use it with events?**
   - Limits function execution frequency; useful for scroll, resize, etc.
   ```javascript
   const throttle = (func, delay) => { /* implementation */ };
   ```

### 32. **What is debouncing in events?**
   - Delays function execution until after event stops.
   ```javascript
   const debounce = (func, delay) => { /* implementation */ };
   ```

### 33. **Difference between throttling and debouncing?**
   - Throttling limits execution rate; debouncing executes after delay.

### 34. **What is `event.detail`?**
   - Contains additional data in custom events.
   ```javascript
   const event = new CustomEvent('custom', { detail: { message: 'Hello' } });
   ```

### 35. **What is a pointer event?**
   - A unified event for mouse, touch, and pen inputs.
   ```javascript
   element.addEventListener('pointerdown', () => console.log('Pointer down!'));
   ```

### 36. **What are passive event listeners?**
   - Indicate that listener won’t call `preventDefault()`, optimizing scrolling.
   ```javascript
   element.addEventListener('scroll', handler, { passive: true });
   ```

### 37. **What is an event loop?**
   - Manages execution of tasks, events, and async operations in JavaScript.

### 38. **What is the `contextmenu` event?**
   - Fires when the right-click menu is triggered.
   ```javascript
   element.addEventListener('contextmenu', (e) => e.preventDefault());
   ```

### 39. **What is `onerror` event?**
   - Catches errors during script execution.
   ```javascript
   window.onerror = (msg, url, line) => console.log(msg);
   ```

### 40. **What is an abort event?**
   - Fires if a resource loading is canceled.
   ```javascript
   image.addEventListener('abort', () => console.log('Image load aborted.'));
   ```

### 41. **What is a submit event?**
   - Fires when a form is submitted.
   ```javascript
   form.addEventListener('submit', (e) => e.preventDefault());
   ```

### 

42. **What is the purpose of `pointer-events` CSS property?**
   - Controls event response on an element, useful for disabling interactions.

### 43. **Difference between passive and active listeners?**
   - Passive listeners don’t call `preventDefault()`; active listeners can.

### 44. **What is the `transitionend` event?**
   - Fires after a CSS transition completes.
   ```javascript
   element.addEventListener('transitionend', () => console.log('Transition ended'));
   ```

### 45. **What is the `animationend` event?**
   - Fires after a CSS animation completes.
   ```javascript
   element.addEventListener('animationend', () => console.log('Animation ended'));
   ```

### 46. **How to prevent event delegation?**
   - Use `stopPropagation()` on the event.

### 47. **What is the `drag` event?**
   - Fires continuously as an element is dragged.

### 48. **How do `load`, `DOMContentLoaded`, and `beforeunload` differ?**
   - `load`: all content loads; `DOMContentLoaded`: DOM loads; `beforeunload`: before leaving page.

### 49. **What is `pointermove` event?**
   - Fires continuously as pointer moves within the target.

### 50. **What is `focusin` and `focusout`?**
   - Bubble versions of `focus` and `blur`, useful for delegation.

-
