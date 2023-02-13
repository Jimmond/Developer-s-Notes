# Pure vs Impure in Javascript

In programming, purity refers to whether or not a function depends on external or static elements. Pure functions only depend on their arguments and have no side effects, that is, they do not modify any external state or produce side effects. Therefore, they always produce the same result for the same arguments.

On the other hand, impure functions depend on external elements or have side effects. This means that they can produce different results for the same arguments depending on the external state or side effects produced.

Purity is important because pure functions are much easier to test, debug and maintain, since their results are predictable and reliable. In addition, pure functions can be combined and composed more easily, which increases code reusability and readability.

In JavaScript, pure functions are those that only depend on their arguments and have no side effects, while impure functions may depend on global variables, modify external states, or produce side effects such as data input/output.

### Here are some examples of pure and impure functions in JavaScript:

*pure* function:

```javascript
function add(a, b) {
  return a + b;
}
```
This function only depends on its arguments `a` and `b` and has no side effects, so it will always produce the same result for the same arguments.

Function *impura*:

```javascript
let counter = 0;

function incrementCounter() {
  counter++;
  return counter;
}
```

This function depends on a global variable `counter` and modifies its value, so it will produce different results for successive calls.

Another example of an *impure* function:

```javascript
function getCurrentTime() {
  return new Date().getTime();
}
```
This function depends on the external state of the current time and will produce different results at different times.

In general, it is recommended to work with pure functions whenever possible to improve the clarity, readability and reliability of the code. However, in some cases it is necessary to work with impure functions to perform operations that require access to external states or produce side effects.