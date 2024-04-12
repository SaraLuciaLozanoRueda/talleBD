# Taller BD


1. Realice la inserción de los siguientes datos.

​	TABLA FABRICANTE

- **fabricante (1,'Asus')**;

```sql
INSERT INTO fabricante (codigo,nombre)

VALUES (1,'Asus');
```

- **fabricante (2,'Lenovo')**;

  ```sql
  INSERT INTO fabricante (codigo,nombre)
  
  VALUES (2,'Lenovo');
  ```

- **fabricante (3,'Hewlett--Packard')**;

  ```sql
  INSERT INTO fabricante (codigo,nombre)
  
  VALUES (3,'Hewlett--Packard');
  ```

- **fabricante (4,'Samsung')**;

  ```sql
  INSERT INTO fabricante (codigo,nombre)
  
  VALUES  (4,'Samsung');
  ```

- **fabricante (5,'Seagate')**;

  ```sql
  INSERT INTO fabricante (codigo,nombre)
  
  VALUES   (5,'Seagate');
  ```

- **fabricante (6,'Crucial')**

  ```sql
  INSERT INTO fabricante (codigo,nombre)
  
  VALUES  (6,'Crucial');
  ```

- **fabricante (7,'Gigabyte')**;

  ```sql
  INSERT INTO fabricante (codigo,nombre)
  
  VALUES   (7,'Gigabyte');
  ```

- **fabricante (8,'Huawei')**;

  ```sql
  INSERT INTO fabricante (codigo,nombre)
  
  VALUES  (8,'Huawei');
  ```

- **fabricante (9,'Xiaomi')**;

```sql
INSERT INTO fabricante (codigo,nombre)

VALUES  (9,'Xiaomi');
```

​	TABLA PRODUCTO

- **producto (1, 'Disco duro SATA3 1TB' ,86.99, 5);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (1, 'Disco duro SATA3 1TB' ,86.99, 5);
  ```

- **producto (2, 'Memoria RAM DDR4 8GB' ,120, 6);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (2, 'Memoria RAM DDR4 8GB' ,120, 6);
  ```

- **producto (3, 'Disco SSD 1 TB', 150.99,  4);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (3, 'Disco SSD 1 TB', 150.99,  4);
  ```

- **producto (4, 'GeForce 1050Ti' , 185 , 7);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (4, 'GeForce 1050Ti' , 185 , 7);
  ```

- **producto (5, 'GeForce 1080 Xtreme' , 755 , 6);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (5, 'GeForce 1080 Xtreme' , 755 , 6);
  ```

- **producto (6, 'Monitor 24 LED Full HD', 202 , 1);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (6, 'Monitor 24 LED Full HD', 202 , 1);
  ```

- **producto (7, 'Monitor 27 LED Full HD', 245.99 , 1);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (7, 'Monitor 27 LED Full HD', 245.99 , 1);
  ```

- **producto (8, 'Portatil Yoga 520', 559 , 2);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (8, 'Portatil Yoga 520', 559 , 2);
  ```

- **producto (9, 'Portatil Ideap 320', 444 , 2);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (9, 'Portatil Ideap 320', 444 , 2);
  ```

- **producto (10, 'Impresora HP Deskjet 3720', 55.99 , 3);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (10, 'Impresora HP Deskjet 3720', 55.99 , 3);
  ```

- **producto (11, 'Impresora HP Laserjet Pro M26nw', 180 , 3);**

  ```sql
  INSERT INTO producto (codigo,nombre,precio,codigo_fabricante)
  
  VALUES  (11, 'Impresora HP Laserjet Pro M26nw', 180 , 3);
  ```



# **Consultas sobre una tabla**

1. Lista el nombre de todos los productos que hay en la tabla producto.

   ```sql
   SELECT nombre
   FROM producto;
   ```

2. Lista los nombres y los precios de todos los productos de la tabla producto.

   ```mysql
   SELECT nombre,precio
   FROM producto;
   ```

3. Lista todas las columnas de la tabla producto.

   ```mysql
   SELECT codigo,nombre,precio,codigo_fabricante
   FROM producto;
   ```

4. Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD).

   ```mysql
   SELECT nombre, (precio/22.09) AS Euro, (precio/19.54) AS Dollar 
   FROM producto;
   ```

5. Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD). Utiliza los siguientes alias para las columnas: nombre de producto, euros, dólares.

   ```mysql
   SELECT nombre AS nombre_de_producto,(precio/22.09) AS euros, (precio/19.54) AS dolares  
   FROM producto;
   ```

6. Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a mayúscula.

   ```mysql
   SELECT UPPER (nombre) AS nombre_mayusculas,precio
   FROM producto
   ```

7. Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a minúscula.

   ```mysql
   SELECT LOWER (nombre) AS nombre_minusculas,precio
   FROM producto
   ```

8. Lista el nombre de todos los fabricantes en una columna, y en otra columna obtenga en mayúsculas los dos primeros caracteres del nombre del fabricante.

   ```mysql
   SELECT nombre AS nombre_fabricante, UPPER(LEFT(nombre, 2)) AS primeros_dos_caracteres
   FROM fabricante;
   ```

9. Lista los nombres y los precios de todos los productos de la tabla producto, redondeando el valor del precio.

   ```mysql
   SELECT nombre,ROUND(precio) AS redondeo
   FROM producto
   ```

10. Lista los nombres y los precios de todos los productos de la tabla producto, truncando el valor del precio para mostrarlo sin ninguna cifra decimal.

    ```mysql
    SELECT nombre,TRUNCATE(precio,0) AS truncado
    FROM producto
    ```

11. Lista el identificador de los fabricantes que tienen productos en la tabla producto.

    ```mysql
    SELECT  DISTINCT codigo_fabricante
    FROM producto
    ```

12. Lista el identificador de los fabricantes que tienen productos en la tabla producto, eliminando los identificadores que aparecen repetidos.

    ```mysql
    SELECT  DISTINCT codigo_fabricante
    FROM producto
    ```

13. Lista los nombres de los fabricantes ordenados de forma ascendente.

    ```mysql
    SELECT  DISTINCT nombre
    FROM fabricante
    ORDER BY nombre 
    ```

14. Lista los nombres de los fabricantes ordenados de forma descendente.

    ```mysql
    SELECT  DISTINCT nombre
    FROM fabricante
    ORDER BY nombre DESC
    ```

15. Lista los nombres de los productos ordenados en primer lugar por el nombre de forma ascendente y en segundo lugar por el precio de forma
    descendente.

    ```mysql
    SELECT nombre, precio
    FROM producto
    ORDER BY nombre ASC, precio DESC;
    ```

16. Devuelve una lista con las 5 primeras filas de la tabla fabricante.

    ```mysql
    SELECT codigo, nombre
    FROM fabricante
    LIMIT 5;
    ```

17. Devuelve una lista con 2 filas a partir de la cuarta fila de la tabla fabricante. La cuarta fila también se debe incluir en la respuesta.

    ```mysql
    SELECT codigo, nombre
    FROM fabricante
    LIMIT 2 OFFSET 3;
    ```

18. Lista el nombre y el precio del producto más barato. (Utilice solamente las cláusulas ORDER BY y LIMIT)

    ```mysql
    SELECT nombre,precio
    FROM producto
    ORDER BY precio ASC
    LIMIT 1
    ```

19. Lista el nombre y el precio del producto más caro. (Utilice solamente las cláusulas ORDER BY y LIMIT)

    ```mysql
    SELECT nombre,precio
    FROM producto
    ORDER BY precio DESC
    LIMIT 1
    ```

20. Lista el nombre de todos los productos del fabricante cuyo identificador de fabricante es igual a 2.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE codigo_fabricante=2
    ```

21. Lista el nombre de los productos que tienen un precio menor o igual a 120€.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE precio<=120
    ```

22. Lista el nombre de los productos que tienen un precio mayor o igual a 400€.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE precio>=400
    ```

23. Lista el nombre de los productos que no tienen un precio mayor o igual a 400€.

    ```mysql
    SELECT nombre,precio
    FROM producto
    WHERE NOT precio>=400
    ```

24. Lista todos los productos que tengan un precio entre 80€ y 300€. Sin utilizar el operador BETWEEN.

    ```mysql
    SELECT nombre,precio
    FROM producto
    WHERE precio >=80 AND precio <=300
    ```

25. Lista todos los productos que tengan un precio entre 60€ y 200€. Utilizando el operador BETWEEN.

    ```mysql
    SELECT nombre,precio
    FROM producto
    WHERE precio BETWEEN 60 AND 200
    ```

26. Lista todos los productos que tengan un precio mayor que 200€ y que el identificador de fabricante sea igual a 6.

    ```mysql
    SELECT nombre,precio,codigo_fabricante
    FROM producto
    WHERE precio>=200 AND codigo_fabricante=6
    ```

27. Lista todos los productos donde el identificador de fabricante sea 1, 3 o 5. Sin utilizar el operador IN.

    ```mysql
    SELECT nombre,codigo_fabricante
    FROM producto
    WHERE codigo_fabricante=1 OR codigo_fabricante=3 OR codigo_fabricante=5
    ```

28. Lista todos los productos donde el identificador de fabricante sea 1, 3 o 5.
    Utilizando el operador IN.

    ```mysql
    SELECT nombre,codigo_fabricante
    FROM producto
    WHERE codigo_fabricante IN (1,3,5)
    ```

29. Lista el nombre y el precio de los productos en céntimos (Habrá que
    multiplicar por 100 el valor del precio). Cree un alias para la columna que
    contiene el precio que se llame céntimos.

    ```mysql
    SELECT nombre,(precio*100) AS centimos
    FROM producto
    ```

30. Lista los nombres de los fabricantes cuyo nombre empiece por la letra S.

    ```mysql
    SELECT nombre
    FROM fabricante
    WHERE nombre LIKE 'S%'
    ```

31. Lista los nombres de los fabricantes cuyo nombre termine por la vocal e.

    ```mysql
    SELECT nombre
    FROM fabricante
    WHERE nombre LIKE '%e'
    ```

32. Lista los nombres de los fabricantes cuyo nombre contenga el carácter w.

    ```mysql
    SELECT nombre
    FROM fabricante
    WHERE nombre LIKE '%w%'
    ```

33. Lista los nombres de los fabricantes cuyo nombre sea de 4 caracteres.

    ```mysql
    SELECT nombre
    FROM fabricante
    WHERE LENGTH(nombre) = 4;
    ```

34. Devuelve una lista con el nombre de todos los productos que contienen la
    cadena Portátil en el nombre.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE nombre LIKE '%Portatil%'
    ```

35. Devuelve una lista con el nombre de todos los productos que contienen la
    cadena Monitor en el nombre y tienen un precio inferior a 215 €.

    ```mysql
    SELECT nombre,precio
    FROM producto
    WHERE nombre LIKE '%Monitor%' AND precio<=215
    ```

36. Lista el nombre y el precio de todos los productos que tengan un precio
    mayor o igual a 180€. Ordene el resultado en primer lugar por el precio (en
    orden descendente) y en segundo lugar por el nombre (en orden
    ascendente).

    ```mysql
    SELECT precio,nombre
    FROM producto
    WHERE precio>=180
    ORDER BY precio DESC,nombre ASC;
    ```

    

    # Consultas multitabla (Composición interna)

    

    Resuelva todas las consultas utilizando la sintaxis de SQL1 y SQL2.

    1. Devuelve una lista con el nombre del producto, precio y nombre de
          fabricante de todos los productos de la base de datos.

       ```sql
       SELECT p.nombre, p.precio,f.nombre
       FROM producto AS p
       INNER JOIN fabricante AS f ON p.codigo_fabricante = f.codigo;
       ```

    2. Devuelve una lista con el nombre del producto, precio y nombre de
          fabricante de todos los productos de la base de datos. Ordene el resultado por el nombre del fabricante, por orden alfabético.

       ```sql
       SELECT p.nombre, p.precio,f.nombre
       FROM producto AS p
       INNER JOIN fabricante AS f ON p.codigo_fabricante = f.codigo
       ORDER BY f.nombre;
       ```

    3. Devuelve una lista con el identificador del producto, nombre del producto,identificador del fabricante y nombre del fabricante, de todos los productos de la base de datos.

       ```sql
       SELECT p.codigo,p.nombre,p.codigo_fabricante,f.nombre
       FROM producto AS p
       INNER JOIN fabricante AS f ON p.codigo_fabricante = f.codigo;
       ```

    4. Devuelve el nombre del producto, su precio y el nombre de su fabricante,
          del producto más barato.

       ```sql
       SELECT p.nombre,p.precio,f.nombre
       FROM producto AS p
       INNER JOIN fabricante AS f ON p.codigo_fabricante = f.codigo
       ORDER BY precio
       LIMIT 1;
       ```

    5. Devuelve el nombre del producto, su precio y el nombre de su fabricante,
          del producto más caro.

       ```sql
       SELECT p.nombre,p.precio,f.nombre
       FROM producto AS p
       INNER JOIN fabricante AS f ON p.codigo_fabricante = f.codigo
       ORDER BY precio DESC
       LIMIT 1;
       ```

    6. Devuelve una lista de todos los productos del fabricante Lenovo.

       ```sql
       SELECT p.nombre,f.nombre
       FROM producto AS p
       INNER JOIN fabricante AS f ON p.codigo_fabricante = f.codigo AND f.nombre='Lenovo'
       ```

    7. Devuelve una lista de todos los productos del fabricante Crucial que tengan un precio mayor que 200€.

       ```sql
       SELECT p.nombre,f.nombre
       FROM producto AS p
       INNER JOIN fabricante AS f ON p.codigo_fabricante = f.codigo AND f.nombre='Crucial' AND precio>200
       ```

    8. Devuelve un listado con todos los productos de los fabricantes Asus, Hewlett-Packardy Seagate. Sin utilizar el operador IN.

       ```sql
       SELECT p.nombre, p.codigo_fabricante, f.nombre
       FROM producto AS p
       JOIN fabricante AS f ON p.codigo_fabricante = f.codigo
       WHERE f.nombre = 'Asus'
       UNION ALL
       SELECT p.nombre, p.codigo_fabricante, f.nombre
       FROM producto AS p
       JOIN fabricante AS f ON p.codigo_fabricante = f.codigo
       WHERE f.nombre = 'Hewlett-Packard'
       UNION ALL
       SELECT p.nombre, p.codigo_fabricante, f.nombre
       FROM producto AS p
       JOIN fabricante AS f ON p.codigo_fabricante = f.codigo
       WHERE f.nombre = 'Seagate';
       ```

    9. Devuelve un listado con todos los productos de los
          fabricantes Asus, Hewlett-Packardy Seagate. Utilizando el operador IN.

       ```sql
       SELECT p.nombre, p.codigo_fabricante, f.nombre
       FROM producto AS p
       JOIN fabricante AS f ON p.codigo_fabricante = f.codigo
       WHERE f.nombre IN ('Asus', 'Hewlett-Packard', 'Seagate');
       ```

    10. Devuelve un listado con el nombre y el precio de todos los productos de los fabricantes cuyo nombre termine por la vocal e

        ```sql
        SELECT p.nombre, p.precio
        FROM producto AS p
        JOIN fabricante AS f ON p.codigo_fabricante = f.codigo
        WHERE f.nombre LIKE '%e'
        ```

    11. Devuelve un listado con el nombre y el precio de todos los productos cuyo nombre de fabricante contenga el carácter w en su nombre.

        ```sql
        SELECT p.nombre, p.precio
        FROM producto AS p
        JOIN fabricante AS f ON p.codigo_fabricante = f.codigo
        WHERE f.nombre LIKE '%w%'
        ```

    12. Devuelve un listado con el nombre de producto, precio y nombre de
        fabricante, de todos los productos que tengan un precio mayor o igual a
        180€. Ordene el resultado en primer lugar por el precio (en orden
        descendente) y en segundo lugar por el nombre (en orden ascendente)

        ```sql
        SELECT p.precio,p.nombre,f.nombre
        FROM producto AS p
        JOIN fabricante AS f ON p.codigo_fabricante = f.codigo AND precio >=180
        ORDER BY precio DESC,p.nombre ASC
        ```

    13. Devuelve un listado con el identificador y el nombre de fabricante,
        solamente de aquellos fabricantes que tienen productos asociados en la
        base de datos.

        ```sql
        SELECT DISTINCT f.codigo,f.nombre
        FROM fabricante AS f
        JOIN producto AS p ON f.codigo =p.codigo_fabricante 
        ```

        



