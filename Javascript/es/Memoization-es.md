# Memoization en javascript

La memoización es una técnica de programación que consiste en almacenar los resultados de una función en una cache para que no tenga que volver a calcularlos la próxima vez que se invoque con los mismos argumentos. Esto se hace para optimizar el rendimiento de la función y reducir la cantidad de cálculos redundantes que realiza.

En JavaScript, la memoización se puede implementar de diferentes maneras, pero una forma común es mediante la creación de un objeto de cache como una propiedad de la función. Cada vez que la función se invoca, se verifica si los resultados ya están almacenados en la cache. Si es así, se devuelve el resultado almacenado en lugar de recalcularlo. Si no, se realiza el cálculo y se almacena el resultado en la cache.

Por ejemplo, aquí hay una implementación de la función de fibonacci con memoización:

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
En este ejemplo, la cache se almacena como una propiedad de la función fibonacci. Cada vez que la función se invoca, se verifica si el resultado ya está almacenado en la cache y, si es así, se devuelve el resultado almacenado en lugar de recalcularlo.

La memoización es una técnica útil para optimizar el rendimiento de funciones costosas y para reducir la cantidad de cálculos redundantes que se realizan en una aplicación. Sin embargo, es importante tener en cuenta que también puede aumentar la cantidad de memoria utilizada por una aplicación, por lo que es importante considerar cuidadosamente cuándo y cómo utilizar la memoización.