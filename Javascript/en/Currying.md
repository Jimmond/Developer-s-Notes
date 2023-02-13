# Currying in javascript

Currying is a functional programming technique that consists of transforming a function that accepts multiple arguments into a sequence of functions that accept a single argument.

In JavaScript, a curried function is a function that returns another function until all required arguments have been provided.

Here is an example of a curried function in JavaScript:

```javascript
function curry(func) {
  return function curried(...args) {
    if (args.length >= func.length) {
      return func.apply(this, args);
    } else {
      return function(...args2) {
        return curried.apply(this, args.concat(args2));
      };
    }
  };
}

function add(a, b, c) {
  return a + b + c;
}

const curriedAdd = curried(add);
const add5 = curriedAdd(5);
const add5And10 = add5(10);
const result = add5And10(15); // returns 30

```
In this example, the `curry` function is a function that takes another function as an argument and converts it into a curried function. The `add` function is a normal function that accepts three arguments. The curried function `curriedAdd` is the result of calling `curry` with `add` as an argument.

The advantage of using curried functions is that it allows you to create more reusable and composable functions. For example, in the example above, we can create an `add5` function that always adds 5 to its argument, and then we can combine this function with other functions to create new functions with more complex behavior.