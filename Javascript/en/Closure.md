# Closure in Javascript

Un closure en JavaScript es una función que se "recuerda" del entorno en el que fue creada. En otras palabras, un closure es una función que retiene el acceso a las variables del ámbito externo una vez que la función ha sido invocada. Esto permite a las funciones recordar y acceder a su entorno incluso después de que se han ejecutado.

Un ejemplo típico de un closure en JavaScript es una función que retorna otra función, como se muestra a continuación:

```javascript
function outerFunction(x) {
  return function innerFunction(y) {
    return x + y;
  }
}

const addFive = outerFunction(5);
console.log(addFive(3)); // 8

```
En este ejemplo, `outerFunction` retorna una función anónima que se guarda en la variable `addFive`. Cuando se invoca `addFive`, esta función tiene acceso al valor de `x` que se pasó a `outerFunction` inicialmente. Por lo tanto, `addFive(3)` devuelve 8.

Los closures son una herramienta poderosa en JavaScript, ya que permiten crear funciones con estado y son útiles para crear funciones que mantienen el contexto y la lógica compartidos. Además, los closures se utilizan comúnmente en la programación funcional para crear funciones de orden superior y para ocultar variables y funciones privadas en el contexto de un objeto.