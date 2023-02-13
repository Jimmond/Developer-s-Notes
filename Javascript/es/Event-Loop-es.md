# ¿Como funciona el Event loop?

El Event Loop es una parte crucial del funcionamiento del asincronismo en JavaScript. Se encarga de administrar la cola de tareas y de ejecutarlas en orden.

El Event Loop funciona de la siguiente manera:

1. Se crea una pila de ejecución (también conocida como la pila de llamados o call stack), que es una estructura de datos que almacena las funciones que deben ser ejecutadas.

2. Se añade la tarea principal o "tarea raíz" a la pila de ejecución.

3. Mientras la pila de ejecución no esté vacía, el Event Loop extrae la siguiente tarea de la pila y la ejecuta.

4. Si durante la ejecución de una tarea se llama a una función asíncrona, esta función no se ejecuta inmediatamente, sino que se añade a la cola de tareas.

5. Una vez que la pila de ejecución está vacía, el Event Loop verifica si hay tareas en la cola de tareas. Si hay tareas en la cola, extrae la siguiente tarea y la añade a la pila de ejecución para ser ejecutada.

6. Este proceso se repite hasta que no haya más tareas en la cola de tareas.

Es importante destacar que el Event Loop es un bucle infinito que se ejecuta constantemente en segundo plano y permite que las tareas asíncronas se ejecuten de manera ordenada y en paralelo con otras tareas. Esto permite que la aplicación respete el orden en el que se han agregado las tareas a la cola de tareas y evita que se bloquee la ejecución del programa mientras se espera el resultado de una operación asíncrona.