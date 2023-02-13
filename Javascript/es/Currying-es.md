# Currying in javascript

Currying es una técnica de programación funcional que consiste en transformar una función que acepta múltiples argumentos en una secuencia de funciones que aceptan un solo argumento.

En JavaScript, una función currificada es una función que retorna otra función hasta que se han proporcionado todos los argumentos necesarios.

Aquí hay un ejemplo de una función currificada en JavaScript:

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

const curriedAdd = curry(add);
const add5 = curriedAdd(5);
const add5And10 = add5(10);
const result = add5And10(15); // returns 30

```
En este ejemplo, la función `curry` es una función que toma otra función como argumento y la convierte en una función currificada. La función `add` es una función normal que acepta tres argumentos. La función currificada `curriedAdd` es el resultado de llamar a `curry` con `add` como argumento.

La ventaja de usar funciones currificadas es que permite crear funciones más reutilizables y composables. Por ejemplo, en el ejemplo anterior, podemos crear una función `add5` que siempre suma 5 a su argumento, y luego podemos combinar esta función con otras funciones para crear nuevas funciones con comportamientos más complejos.