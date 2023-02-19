# Transact SQL

## Principios T-SQL

T-SQL (Transact-SQL) es una extensión de SQL (Structured Query Language) que se utiliza en Microsoft SQL Server. Algunos de los principios fundamentales de T-SQL son:

1. Declarativo: T-SQL es un lenguaje de programación declarativo, lo que significa que se describe lo que se quiere hacer en lugar de cómo hacerlo. En lugar de especificar cada paso para lograr un objetivo, se le dice al motor de base de datos lo que se quiere y este se encarga de determinar la mejor manera de hacerlo.

2. Comandos DML, DDL y DCL: T-SQL es un lenguaje que admite comandos DML (Data Manipulation Language), como SELECT, INSERT, UPDATE y DELETE, que se utilizan para trabajar con los datos en las tablas de una base de datos. También admite comandos DDL (Data Definition Language), como CREATE, ALTER y DROP, que se utilizan para crear, modificar y eliminar objetos de la base de datos, como tablas, vistas y procedimientos almacenados. Finalmente, admite comandos DCL (Data Control Language), como GRANT y REVOKE, que se utilizan para controlar el acceso a los objetos de la base de datos.

3. Transacciones: T-SQL admite transacciones, lo que significa que un conjunto de instrucciones se puede agrupar en una transacción que se ejecuta de manera atómica (todo o nada). Si una transacción falla en algún momento, se deshace todo lo que se hizo hasta ese punto. Las transacciones aseguran que las operaciones se completen con éxito y mantienen la integridad de los datos.

4. Funciones: T-SQL admite funciones, que son bloques de código que aceptan ciertos parámetros, realizan una tarea específica y devuelven un valor. Las funciones pueden ser escalares, tabulares o de ventana.

5. Procedimientos almacenados: T-SQL admite procedimientos almacenados, que son programas que se almacenan en la base de datos y se pueden ejecutar desde cualquier lugar donde se pueda conectarse a la base de datos. Los procedimientos almacenados son una forma conveniente de encapsular la lógica de negocio en la base de datos y de evitar la repetición de código.

6. Cursores: T-SQL admite cursores, que se utilizan para recorrer filas de una tabla una por una y realizar operaciones en ellas. Los cursores son útiles cuando es necesario realizar operaciones que no se pueden realizar mediante comandos DML regulares, como actualizar una columna en función del valor de otra columna.

Estos son solo algunos de los principios fundamentales de T-SQL. La comprensión de estos principios es importante para escribir consultas eficientes y efectivas que permitan obtener y manipular los datos de una base de datos de manera adecuada.

## Diferencias entre SQL y T-SQL

SQL (Structured Query Language) es un lenguaje de programación utilizado para interactuar con bases de datos relacionales. t-SQL (Transact-SQL) es una implementación de SQL que agrega características adicionales a las ya existentes en SQL.

A continuación, se presentan algunas diferencias entre SQL y t-SQL:

- Funciones: t-SQL incluye un conjunto de funciones adicionales a las presentes en SQL. Por ejemplo, t-SQL tiene funciones de ventana que permiten realizar cálculos basados en particiones de datos. También incluye funciones para la manipulación de cadenas de texto y fechas.

- Disparadores (Triggers): Los disparadores de t-SQL tienen mayor capacidad que los de SQL. t-SQL permite la creación de disparadores para varios eventos, incluyendo la inserción, actualización y eliminación de datos.

- Procedimientos almacenados: t-SQL permite la creación de procedimientos almacenados que pueden tener parámetros de entrada y salida, lo que permite la reutilización de código y la reducción de la complejidad en la lógica de negocio.

- Control de flujo: t-SQL tiene una mayor capacidad de control de flujo que SQL. Por ejemplo, t-SQL permite el uso de estructuras condicionales como IF-ELSE y bucles como WHILE.

- Transacciones: t-SQL ofrece una mayor capacidad para trabajar con transacciones que SQL. Por ejemplo, t-SQL permite la definición de transacciones anidadas y la capacidad de especificar el nivel de aislamiento de la transacción.

En resumen, t-SQL es una versión extendida de SQL que ofrece características adicionales para la administración de bases de datos y la manipulación de datos.

## Ejemplos T-SQL

1. Funciones
Ejemplo de función de ventana en t-SQL:

```SQL
SELECT CustomerID, OrderDate, TotalAmount, SUM(TotalAmount) OVER(PARTITION BY CustomerID ORDER BY OrderDate) AS RunningTotal
FROM Orders

```
2. Disparadores (Triggers)
Ejemplo de disparador AFTER INSERT en t-SQL:

```SQL
CREATE TRIGGER tr_InsertOrder
ON Orders
AFTER INSERT
AS
BEGIN
    -- Lógica de negocio aquí
END

```

3. Procedimientos almacenados
Ejemplo de procedimiento almacenado con parámetros en t-SQL:

```SQL
CREATE PROCEDURE GetOrdersByCustomerID
    @CustomerID int
AS
BEGIN
    SELECT OrderID, OrderDate, TotalAmount
    FROM Orders
    WHERE CustomerID = @CustomerID
END

```

4. Control de flujo
Ejemplo de estructura condicional IF-ELSE en t-SQL:

```SQL
IF @TotalAmount > 100
BEGIN
    PRINT 'Descuento aplicado'
    SET @TotalAmount = @TotalAmount * 0.9
END
ELSE
BEGIN
    PRINT 'No se aplicó descuento'
END

```
5. Transacciones
Ejemplo de transacción anidada en t-SQL:

```SQL
BEGIN TRANSACTION OuterTransaction
    -- Lógica de negocio aquí
    BEGIN TRANSACTION InnerTransaction
        -- Lógica de negocio aquí
    COMMIT TRANSACTION InnerTransaction
COMMIT TRANSACTION OuterTransaction

```