# First Order/Higher order in Javascript

En programación, la orden de una función se refiere a su capacidad de trabajar con otras funciones.

Las funciones de orden superior son aquellas que aceptan otras funciones como argumentos o que devuelven funciones como resultados. Esto les permite realizar operaciones más complejas y combinar funciones de manera más efectiva.

Por otro lado, las funciones de orden uno (también conocidas como funciones de primer orden) son aquellas que solo aceptan y devuelven valores simples, como números, cadenas o objetos.

En JavaScript, todas las funciones son de orden superior, ya que pueden aceptar y devolver funciones como argumentos y resultados.

Aquí hay un ejemplo de una función de orden superior en JavaScript:

```javascript
function higherOrderFunction(func) {
  return func(5);
}

function add(a) {
  return a + 5;
}

higherOrderFunction(add); // returns 10

```
En este ejemplo, la función `higherOrderFunction` es una función de orden superior, ya que acepta otra función `add` como argumento y la ejecuta.

Las funciones de orden superior son una característica importante de la programación funcional, y se utilizan a menudo para crear código más legible, reutilizable y fácil de mantener.