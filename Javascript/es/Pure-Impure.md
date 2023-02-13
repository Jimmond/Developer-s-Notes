# Pure vs Impure en Javascript

En programación, la pureza se refiere a si una función depende o no de elementos externos o estáticos. Las funciones puras solo dependen de sus argumentos y no tienen efectos secundarios, es decir, no modifican ningún estado externo ni producen efectos secundarios. Por lo tanto, siempre producen el mismo resultado para los mismos argumentos.

Por otro lado, las funciones impuras dependen de elementos externos o tienen efectos secundarios. Esto significa que pueden producir resultados diferentes para los mismos argumentos dependiendo del estado externo o de los efectos secundarios producidos.

La pureza es importante porque las funciones puras son mucho más fáciles de testear, depurar y mantener, ya que sus resultados son previsibles y confiables. Además, las funciones puras se pueden combinar y composicionar de manera más fácil, lo que aumenta la reutilización y la legibilidad del código.

En JavaScript, las funciones puras son las que solo dependen de sus argumentos y no tienen efectos secundarios, mientras que las funciones impuras pueden depender de variables globales, modificar estados externos o producir efectos secundarios como la entrada/salida de datos.

### Aquí hay algunos ejemplos de funciones puras y impuras en JavaScript:

Función *pura*:

```javascript
function add(a, b) {
  return a + b;
}
```
Esta función solo depende de sus argumentos `a` y `b` y no tiene efectos secundarios, por lo que siempre producirá el mismo resultado para los mismos argumentos.

Función *impura*:

```javascript
let counter = 0;

function incrementCounter() {
  counter++;
  return counter;
}
```

Esta función depende de una variable global `counter` y modifica su valor, por lo que producirá resultados diferentes para llamadas sucesivas.

Otro ejemplo de función *impura*:

```javascript
function getCurrentTime() {
  return new Date().getTime();
}
```
Esta función depende del estado externo de la hora actual y producirá diferentes resultados en diferentes momentos.

En general, se recomienda trabajar con funciones puras siempre que sea posible para mejorar la claridad, la legibilidad y la fiabilidad del código. Sin embargo, en algunos casos es necesario trabajar con funciones impuras para realizar operaciones que requieren acceso a estados externos o producir efectos secundarios.