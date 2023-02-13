# Closure in JavaScript

A closure in JavaScript is a function that "remembers" the environment in which it was created. In other words, a closure is a function that retains access to variables in the outer scope once the function has been invoked. This allows functions to remember and access their environment even after they have been executed.

A typical example of a closure in JavaScript is a function that returns another function, as shown below:

```javascript
function outerFunction(x) {
  return function innerFunction(y) {
    return x + y;
  }
}

const addFive = outerFunction(5);
console.log(addFive(3)); // 8

```
In this example, `outerFunction` returns an anonymous function that is stored in the `addFive` variable. When `addFive` is invoked, this function has access to the value of `x` that was passed to `outerFunction` initially. Therefore, `addFive(3)` returns 8.

Closures are a powerful tool in JavaScript, as they allow you to create stateful functions and are useful for creating functions that maintain shared context and logic. In addition, closures are commonly used in functional programming to create higher-order functions and to hide private variables and functions in the context of an object.