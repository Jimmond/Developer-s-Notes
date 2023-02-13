# First Order/Higher order in Javascript

In programming, the order of a function refers to its ability to work with other functions.

Higher-order functions are those that accept other functions as arguments or return functions as results. This allows them to perform more complex operations and combine functions more effectively.

On the other hand, first-order functions (also known as first-order functions) are those that only accept and return simple values, such as numbers, strings or objects.

In JavaScript, all functions are higher order, since they can accept and return functions as arguments and results.

Here is an example of a higher-order function in JavaScript:

```javascript
function higherOrderFunction(func) {
  return func(5);
}

function add(a) {
  return a + 5;
}

higherOrderFunction(add); // returns 10.

```
In this example, the `higherOrderFunction` function is a higher-order function, since it accepts another `add` function as an argument and executes it.

Higher-order functions are an important feature of functional programming and are often used to create more readable, reusable, and maintainable code.