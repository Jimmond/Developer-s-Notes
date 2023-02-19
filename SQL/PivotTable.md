# Pivot table

Una tabla dinámica (pivot table en inglés) en SQL es una tabla que transforma datos de una tabla en un formato diferente para facilitar su análisis. En una tabla dinámica, las filas y columnas se intercambian para mostrar resúmenes de datos en una forma más legible.

Para crear una tabla dinámica en SQL, se utiliza la función PIVOT, que realiza la transformación de datos. La sintaxis básica para crear una tabla dinámica en SQL es la siguiente:

```SQL
SELECT columnas-agrupación
FROM tabla
PIVOT (función-agregado(columna-valor)
       FOR columna-columna-en-resultado IN (valor-1, valor-2, ..., valor-n)) AS alias

```

Donde:

* columnas-agrupación: son las columnas que se utilizarán para agrupar los datos.
* tabla: es la tabla de origen de los datos.
* función-agregado: es la función de agregado que se utilizará para resumir los datos. Por ejemplo, SUM, COUNT, AVG, entre otras.
* columna-valor: es la columna que contiene los valores que se resumirán.
* columna-columna-en-resultado: es la columna que se utilizará para crear las columnas en la tabla dinámica.
* valor-1, valor-2, ..., valor-n: son los valores únicos de la columna-columna-en-resultado que se utilizarán para crear las columnas en la tabla dinámica.
* alias: es el nombre que se le dará a la tabla dinámica resultante.

A continuación, te proporciono un ejemplo de una tabla dinámica en SQL utilizando la función PIVOT:

Supongamos que tenemos una tabla llamada "ventas" que contiene información de ventas de productos en diferentes tiendas:

```sql
+------------+-------+-------+-------+
| Fecha      | Tienda| Producto | Ventas |
+------------+-------+-------+-------+
| 2022-01-01 | A     | X     | 10    |
| 2022-01-01 | A     | Y     | 20    |
| 2022-01-01 | B     | X     | 15    |
| 2022-01-01 | B     | Y     | 25    |
| 2022-01-02 | A     | X     | 12    |
| 2022-01-02 | A     | Y     | 22    |
| 2022-01-02 | B     | X     | 16    |
| 2022-01-02 | B     | Y     | 26    |
+------------+-------+-------+-------+

```
Queremos crear una tabla dinámica que muestre las ventas totales de cada producto por tienda en cada fecha. Para hacer esto, podemos usar la siguiente consulta:

```sql
SELECT Fecha, Tienda, X, Y
FROM (
    SELECT Fecha, Tienda, Producto, Ventas
    FROM ventas
) AS t
PIVOT (
    SUM(Ventas)
    FOR Producto IN (X, Y)
) AS p

```
El resultado sería:

```sql
+------------+-------+----+----+
| Fecha      | Tienda| X  | Y  |
+------------+-------+----+----+
| 2022-01-01 | A     | 10 | 20 |
| 2022-01-01 | B     | 15 | 25 |
| 2022-01-02 |

```