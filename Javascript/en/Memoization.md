# Memoization in Javascript

Memoization is a programming technique that consists of storing the results of a function in a cache so that it does not have to recalculate them the next time it is invoked with the same arguments. This is done to optimize the performance of the function and reduce the amount of redundant calculations it performs.

In JavaScript, memoization can be implemented in different ways, but a common way is by creating a cache object as a property of the function. Each time the function is invoked, it checks to see if the results are already stored in the cache. If so, the stored result is returned instead of recalculating it. If not, the calculation is performed and the result is stored in the cache.

For example, here is an implementation of the fibonacci function with memoization:

```javascript
function fibonacci(n) {
  if (!fibonacci.cache) {
    fibonacci.cache = {};
  }

  if (fibonacci.cache[n]) {
    return fibonacci.cache[n];
  }

  if (n <= 1) {
    return n;
  }

  let result = fibonacci(n - 1) + fibonacci(n - 2);
  fibonacci.cache[n] = result;
  return result;
}
```
In this example, the cache is stored as a property of the fibonacci function. Each time the function is invoked, it checks whether the result is already stored in the cache and, if so, returns the stored result instead of recalculating it.

Memoization is a useful technique to optimize the performance of expensive functions and to reduce the amount of redundant computations performed in an application. However, it is important to note that it can also increase the amount of memory used by an application, so it is important to carefully consider when and how to use memoization.