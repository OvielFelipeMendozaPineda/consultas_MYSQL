# EJERCICIOS CONSULTAS EN MYjsx

#### 	1. Consultas sobre una tabla.

1. Lista el primer apellido de todos los empleados.

   ```jsx
   SELECT apellido1 FROM empleado;
   +-----------+
   | apellido1 |
   +-----------+
   | Rivero    |
   | Salas     |
   | Rubio     |
   | Suárez    |
   | Loyola    |
   | Santana   |
   | Ruiz      |
   | Ruiz      |
   | Gómez     |
   | Flores    |
   | Herrera   |
   | Salas     |
   | Sáez      |
   +-----------+
   ```

   

2. Lista el primer apellido de los empleados eliminando los apellidos que estén
    repetidos.

  ```jsx
  SELECT DISTINCT apellido1 FROM empleado;
  +-----------+
  | apellido1 |
  +-----------+
  | Rivero    |
  | Salas     |
  | Rubio     |
  | Suárez    |
  | Loyola    |
  | Santana   |
  | Ruiz      |
  | Gómez     |
  | Flores    |
  | Herrera   |
  | Sáez      |
  +-----------+
  ```

3. Lista todas las columnas de la tabla empleado.

     ```jsx
     SELECT id, nif, nombre, apellido1, apellido2, id_departamento  FROM empleado;
     +----+-----------+--------------+-----------+-----------+-----------------+
     | id | nif       | nombre       | apellido1 | apellido2 | id_departamento |
     +----+-----------+--------------+-----------+-----------+-----------------+
     |  1 | 32481596F | Aarón        | Rivero    | Gómez     |               1 |
     |  2 | Y5575632D | Adela        | Salas     | Díaz      |               2 |
     |  3 | R6970642B | Adolfo       | Rubio     | Flores    |               3 |
     |  4 | 77705545E | Adrián       | Suárez    | NULL      |               4 |
     |  5 | 17087203C | Marcos       | Loyola    | Méndez    |               5 |
     |  6 | 38382980M | María        | Santana   | Moreno    |               1 |
     |  7 | 80576669X | Pilar        | Ruiz      | NULL      |               2 |
     |  8 | 71651431Z | Pepe         | Ruiz      | Santana   |               3 |
     |  9 | 56399183D | Juan         | Gómez     | López     |               2 |
     | 10 | 46384486H | Diego        | Flores    | Salas     |               5 |
     | 11 | 67389283A | Marta        | Herrera   | Gil       |               1 |
     | 12 | 41234836R | Irene        | Salas     | Flores    |            NULL |
     | 13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |            NULL |
     +----+-----------+--------------+-----------+-----------+-----------------+
     
     ```

     

4. Lista el nombre y los apellidos de todos los empleados.

     ```jsx
     SELECT nombre, apellido1, apellido2 FROM empleado;
     +--------------+-----------+-----------+
     | nombre       | apellido1 | apellido2 |
     +--------------+-----------+-----------+
     | Aarón        | Rivero    | Gómez     |
     | Adela        | Salas     | Díaz      |
     | Adolfo       | Rubio     | Flores    |
     | Adrián       | Suárez    | NULL      |
     | Marcos       | Loyola    | Méndez    |
     | María        | Santana   | Moreno    |
     | Pilar        | Ruiz      | NULL      |
     | Pepe         | Ruiz      | Santana   |
     | Juan         | Gómez     | López     |
     | Diego        | Flores    | Salas     |
     | Marta        | Herrera   | Gil       |
     | Irene        | Salas     | Flores    |
     | Juan Antonio | Sáez      | Guerrero  |
     +--------------+-----------+-----------+
     ```

     

5. Lista el identificador de los departamentos de los empleados que aparecen
     en la tabla empleado.

     ```jsx
     SELECT id_departamento FROM empleado WHERE id_departamento IS NOT NULL;
     +-----------------+
     | id_departamento |
     +-----------------+
     |               1 |
     |               1 |
     |               1 |
     |               2 |
     |               2 |
     |               2 |
     |               3 |
     |               3 |
     |               4 |
     |               5 |
     |               5 |
     ```

6. Lista el identificador de los departamentos de los empleados que aparecen
     en la tabla empleado, eliminando los identificadores que aparecen repetidos.

     ```jsx
     SELECT DISTINCT id_departamento FROM empleado WHERE id_departamento IS NOT NULL;
     +-----------------+
     | id_departamento |
     +-----------------+
     |               1 |
     |               2 |
     |               3 |
     |               4 |
     |               5 |
     +-----------------+
     
     ```

7. Lista el nombre y apellidos de los empleados en una única columna. 

     ```jsx
     SELECT CONCAT(nombre, ' ', apellido1, ' ', apellido2) as nombreCompleto FROM empleado;
     +----------------------------+
     | nombreCompleto             |
     +----------------------------+
     | Aarón Rivero Gómez         |
     | Adela Salas Díaz           |
     | Adolfo Rubio Flores        |
     | NULL                       |
     | Marcos Loyola Méndez       |
     | María Santana Moreno       |
     | NULL                       |
     | Pepe Ruiz Santana          |
     | Juan Gómez López           |
     | Diego Flores Salas         |
     | Marta Herrera Gil          |
     | Irene Salas Flores         |
     | Juan Antonio Sáez Guerrero |
     +----------------------------+
     
     ```

8. Lista el nombre y apellidos de los empleados en una única columna, convirtiendo todos los caracteres en mayúscula.

     ```jsx
     SELECT UPPER(CONCAT( nombre, ' ', apellido1, ' ', apellido2)) as nombreCompleto FROM empleado;
     +----------------------------+
     | nombreCompleto             |
     +----------------------------+
     | AARÓN RIVERO GÓMEZ         |
     | ADELA SALAS DÍAZ           |
     | ADOLFO RUBIO FLORES        |
     | NULL                       |
     | MARCOS LOYOLA MÉNDEZ       |
     | MARÍA SANTANA MORENO       |
     | NULL                       |
     | PEPE RUIZ SANTANA          |
     | JUAN GÓMEZ LÓPEZ           |
     | DIEGO FLORES SALAS         |
     | MARTA HERRERA GIL          |
     | IRENE SALAS FLORES         |
     | JUAN ANTONIO SÁEZ GUERRERO |
     +----------------------------+
     ```

     

9. Lista el nombre y apellidos de los empleados en una única columna, convirtiendo todos los caracteres en minúscula.

     ```jsx
     SELECT LOWER(CONCAT( nombre, ' ', apellido1, ' ', apellido2)) as nombreCompleto FROM empleado;
     +----------------------------+
     | nombreCompleto             |
     +----------------------------+
     | aarón rivero gómez         |
     | adela salas díaz           |
     | adolfo rubio flores        |
     | NULL                       |
     | marcos loyola méndez       |
     | maría santana moreno       |
     | NULL                       |
     | pepe ruiz santana          |
     | juan gómez lópez           |
     | diego flores salas         |
     | marta herrera gil          |
     | irene salas flores         |
     | juan antonio sáez guerrero |
     +----------------------------+
     ```

     

10. Lista el identificador de los empleados junto al nif, pero el nif deberá aparecer en dos columnas, una mostrará únicamente los dígitos del nif y la otra la letra. 

     ```jsx
       SELECT id,
       REGEXP_REPLACE(nif, '[^0-9]', '') AS nif_numeros,
       REGEXP_REPLACE(nif, '[^A-Za-z]', '') AS nif_letras
       FROM empleado;
       +----+-------------+------------+
     | id | nif_numeros | nif_letras |
     +----+-------------+------------+
     |  1 | 32481596    | F          |
     |  2 | 5575632     | YD         |
     |  3 | 6970642     | RB         |
     |  4 | 77705545    | E          |
     |  5 | 17087203    | C          |
     |  6 | 38382980    | M          |
     |  7 | 80576669    | X          |
     |  8 | 71651431    | Z          |
     |  9 | 56399183    | D          |
     | 10 | 46384486    | H          |
     | 11 | 67389283    | A          |
     | 12 | 41234836    | R          |
     | 13 | 82635162    | B          |
     +----+-------------+------------+
     ```

     ​    

11. Lista el nombre de cada departamento y el valor del presupuesto actual del
          que dispone. Para calcular este dato tendrá que restar al valor del
          presupuesto inicial (columna presupuesto) los gastos que se han generado
          (columna gastos). Tenga en cuenta que en algunos casos pueden existir
          valores negativos. Utilice un alias apropiado para la nueva columna columna
          que está calculando.

        ```jsx
        SELECT presupuesto - gastos as presupuesto_actual
        FROM departamento;
        +--------------------+
        | presupuesto_actual |
        +--------------------+
        |             114000 |
        |             129000 |
        |             255000 |
        |             107000 |
        |              -5000 |
        |                  0 |
        |              -1000 |
        +--------------------+
        
        ```

    
    ​    
    
12. Lista el nombre de los departamentos y el valor del presupuesto actual
          ordenado de forma ascendente.

        ```jsx
        SELECT nombre, presupuesto - gastos as presupuesto_actual
        FROM departamento
        ORDER BY presupuesto_actual ASC;
        +------------------+--------------------+
        | nombre           | presupuesto_actual |
        +------------------+--------------------+
        | I+D              |              -5000 |
        | Publicidad       |              -1000 |
        | Proyectos        |                  0 |
        | Contabilidad     |             107000 |
        | Desarrollo       |             114000 |
        | Sistemas         |             129000 |
        | Recursos Humanos |             255000 |
        +------------------+--------------------+
        ```

    
    ​    
    
13. Lista el nombre de todos los departamentos ordenados de forma
          ascendente.

      ```jsx
      SELECT nombre FROM departamento ORDER BY nombre ASC;
      +------------------+
      | nombre           |
      +------------------+
      | Contabilidad     |
      | Desarrollo       |
      | I+D              |
      | Proyectos        |
      | Publicidad       |
      | Recursos Humanos |
      | Sistemas         |
      +------------------+
      ```

14. Lista el nombre de todos los departamentos ordenados de forma
          descendente.

      ```jsx
      SELECT nombre FROM departamento ORDER BY nombre DESC;
      +------------------+
      | nombre           |
      +------------------+
      | Sistemas         |
      | Recursos Humanos |
      | Publicidad       |
      | Proyectos        |
      | I+D              |
      | Desarrollo       |
      | Contabilidad     |
      +------------------+
      ```

      

15. Lista los apellidos y el nombre de todos los empleados, ordenados de forma
          alfabética tendiendo en cuenta en primer lugar sus apellidos y luego su
          nombre.

      ```jsx
      SELECT apellido1, apellido2, nombre 
      FROM empleado
      ORDER BY apellido1, apellido2 ASC;
      +-----------+-----------+--------------+
      | apellido1 | apellido2 | nombre       |
      +-----------+-----------+--------------+
      | Flores    | Salas     | Diego        |
      | Gómez     | López     | Juan         |
      | Herrera   | Gil       | Marta        |
      | Loyola    | Méndez    | Marcos       |
      | Rivero    | Gómez     | Aarón        |
      | Rubio     | Flores    | Adolfo       |
      | Ruiz      | NULL      | Pilar        |
      | Ruiz      | Santana   | Pepe         |
      | Sáez      | Guerrero  | Juan Antonio |
      | Salas     | Díaz      | Adela        |
      | Salas     | Flores    | Irene        |
      | Santana   | Moreno    | María        |
      | Suárez    | NULL      | Adrián       |
      +-----------+-----------+--------------+
      ```

16. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos
          que tienen mayor presupuesto.

      ```jsx
      SELECT nombre, presupuesto FROM departamento ORDER BY presupuesto DESC LIMIT 3;
      +------------------+-------------+
      | nombre           | presupuesto |
      +------------------+-------------+
      | I+D              |      375000 |
      | Recursos Humanos |      280000 |
      | Sistemas         |      150000 |
      +------------------+-------------+
      ```

      

17. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos
          que tienen menor presupuesto.

      ```jsx
      SELECT nombre, presupuesto FROM departamento ORDER BY presupuesto ASC LIMIT 3;
      +--------------+-------------+
      | nombre       | presupuesto |
      +--------------+-------------+
      | Proyectos    |           0 |
      | Publicidad   |           0 |
      | Contabilidad |      110000 |
      +--------------+-------------+
      ```

      

18. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que
          tienen mayor gasto.

      ```jsx
      SELECT nombre, gastos FROM departamento ORDER BY gastos DESC LIMIT 2;
      +------------------+--------+
      | nombre           | gastos |
      +------------------+--------+
      | I+D              | 380000 |
      | Recursos Humanos |  25000 |
      +------------------+--------+
      ```

      

19. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que
          tienen menor gasto.

      ```jsx
      SELECT nombre, gastos FROM departamento ORDER BY gastos ASC LIMIT 2;
      +------------+--------+
      | nombre     | gastos |
      +------------+--------+
      | Proyectos  |      0 |
      | Publicidad |   1000 |
      +------------+--------+
      ```

      

20. Devuelve una lista con 5 filas a partir de la tercera fila de la tabla empleado. La
          tercera fila se debe incluir en la respuesta. La respuesta debe incluir todas las
          columnas de la tabla empleado.

      ```jsx
      SELECT id, nif, nombre, apellido1, apellido2, id_departamento FROM empleado LIMIT 5 OFFSET 2;
      +----+-----------+--------+-----------+-----------+-----------------+
      | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
      +----+-----------+--------+-----------+-----------+-----------------+
      |  3 | R6970642B | Adolfo | Rubio     | Flores    |               3 |
      |  4 | 77705545E | Adrián | Suárez    | NULL      |               4 |
      |  5 | 17087203C | Marcos | Loyola    | Méndez    |               5 |
      |  6 | 38382980M | María  | Santana   | Moreno    |               1 |
      |  7 | 80576669X | Pilar  | Ruiz      | NULL      |               2 |
      +----+-----------+--------+-----------+-----------+-----------------+
      ```

      

21. Devuelve una lista con el nombre de los departamentos y el presupuesto, de
          aquellos que tienen un presupuesto mayor o igual a 150000 euros.

      ```jsx
      SELECT nombre, presupuesto FROM departamento WHERE presupuesto >= 150000;
      +------------------+-------------+
      | nombre           | presupuesto |
      +------------------+-------------+
      | Sistemas         |      150000 |
      | Recursos Humanos |      280000 |
      | I+D              |      375000 |
      +------------------+-------------+
      ```

22. Devuelve una lista con el nombre de los departamentos y el gasto, de
          aquellos que tienen menos de 5000 euros de gastos.

      ```jsx
      SELECT nombre, presupuesto FROM departamento WHERE presupuesto <= 500;
      +------------+-------------+
      | nombre     | presupuesto |
      +------------+-------------+
      | Proyectos  |           0 |
      | Publicidad |           0 |
      +------------+-------------+
      ```

      

23. Devuelve una lista con el nombre de los departamentos y el presupuesto, de
          aquellos que tienen un presupuesto entre 100000 y 200000 euros. Sin
          utilizar el operador BETWEEN.

      ```jsx
      SELECT nombre, presupuesto FROM departamento WHERE presupuesto >= 100000 AND presupuesto <= 200000;
      +--------------+-------------+
      | nombre       | presupuesto |
      +--------------+-------------+
      | Desarrollo   |      120000 |
      | Sistemas     |      150000 |
      | Contabilidad |      110000 |
      +--------------+-------------+
      ```

      

24. Devuelve una lista con el nombre de los departamentos que no tienen un
          presupuesto entre 100000 y 200000 euros. Sin utilizar el operador BETWEEN.

      ```jsx
      SELECT  nombre, presupuesto FROM departamento WHERE presupuesto <= 100000 OR presupuesto >= 200000;
      +------------------+-------------+
      | nombre           | presupuesto |
      +------------------+-------------+
      | Recursos Humanos |      280000 |
      | I+D              |      375000 |
      | Proyectos        |           0 |
      | Publicidad       |           0 |
      +------------------+-------------+
      ```

      

25. Devuelve una lista con el nombre de los departamentos que tienen un
          presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN.

      ```jsx
      SELECT nombre, presupuesto FROM departamento WHERE presupuesto BETWEEN 100000 AND 200000;
      +--------------+-------------+
      | nombre       | presupuesto |
      +--------------+-------------+
      | Desarrollo   |      120000 |
      | Sistemas     |      150000 |
      | Contabilidad |      110000 |
      +--------------+-------------+
      ```

      

26. Devuelve una lista con el nombre de los departamentos que no tienen un
          presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN.

      ```jsx
      SELECT nombre, presupuesto FROM departamento WHERE presupuesto NOT BETWEEN 100000 AND 200000;
      +------------------+-------------+
      | nombre           | presupuesto |
      +------------------+-------------+
      | Recursos Humanos |      280000 |
      | I+D              |      375000 |
      | Proyectos        |           0 |
      | Publicidad       |           0 |
      +------------------+-------------+
      ```

      

27. Devuelve una lista con el nombre de los departamentos, gastos y
          presupuesto, de aquellos departamentos donde los gastos sean mayores
          que el presupuesto del que disponen.

      ```jsx
      SELECT nombre, gastos, presupuesto FROM departamento WHERE gastos > presupuesto;
      +------------+--------+-------------+
      | nombre     | gastos | presupuesto |
      +------------+--------+-------------+
      | I+D        | 380000 |      375000 |
      | Publicidad |   1000 |           0 |
      +------------+--------+-------------+
      ```

      

28. Devuelve una lista con el nombre de los departamentos, gastos y
          presupuesto, de aquellos departamentos donde los gastos sean menores
          que el presupuesto del que disponen.

      ```jsx
      SELECT nombre, gastos, presupuesto FROM departamento WHERE gastos < presupuesto; 
      +------------------+--------+-------------+
      | nombre           | gastos | presupuesto |
      +------------------+--------+-------------+
      | Desarrollo       |   6000 |      120000 |
      | Sistemas         |  21000 |      150000 |
      | Recursos Humanos |  25000 |      280000 |
      | Contabilidad     |   3000 |      110000 |
      +------------------+--------+-------------+
      ```

      

29. Devuelve una lista con el nombre de los departamentos, gastos y
          presupuesto, de aquellos departamentos donde los gastos sean iguales al
          presupuesto del que disponen.

      ```jsx
      SELECT nombre, gastos, presupuesto FROM departamento WHERE gastos = presupuesto;
       +-----------+--------+-------------+
      | nombre    | gastos | presupuesto |
      +-----------+--------+-------------+
      | Proyectos |      0 |           0 |
      +-----------+--------+-------------+
      ```

      

30. Lista todos los datos de los empleados cuyo segundo apellido sea NULL.

      ```jsx
      SELECT id, nif, nombre, apellido1, apellido2, id_departamento FROM empleado WHERE apellido2 IS NULL;
      +----+-----------+--------+-----------+-----------+-----------------+
      | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
      +----+-----------+--------+-----------+-----------+-----------------+
      |  4 | 77705545E | Adrián | Suárez    | NULL      |               4 |
      |  7 | 80576669X | Pilar  | Ruiz      | NULL      |               2 |
      +----+-----------+--------+-----------+-----------+-----------------+
      ```

      

31. Lista todos los datos de los empleados cuyo segundo apellido no sea NULL.

      ```jsx
      SELECT id, nif, nombre, apellido1, apellido2, id_departamento FROM empleado WHERE apellido2 IS NOT NULL;
      +----+-----------+--------------+-----------+-----------+-----------------+
      | id | nif       | nombre       | apellido1 | apellido2 | id_departamento |
      +----+-----------+--------------+-----------+-----------+-----------------+
      |  1 | 32481596F | Aarón        | Rivero    | Gómez     |               1 |
      |  2 | Y5575632D | Adela        | Salas     | Díaz      |               2 |
      |  3 | R6970642B | Adolfo       | Rubio     | Flores    |               3 |
      |  5 | 17087203C | Marcos       | Loyola    | Méndez    |               5 |
      |  6 | 38382980M | María        | Santana   | Moreno    |               1 |
      |  8 | 71651431Z | Pepe         | Ruiz      | Santana   |               3 |
      |  9 | 56399183D | Juan         | Gómez     | López     |               2 |
      | 10 | 46384486H | Diego        | Flores    | Salas     |               5 |
      | 11 | 67389283A | Marta        | Herrera   | Gil       |               1 |
      | 12 | 41234836R | Irene        | Salas     | Flores    |            NULL |
      | 13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |            NULL |
      +----+-----------+--------------+-----------+-----------+-----------------+
      ```

      

32. Lista todos los datos de los empleados cuyo segundo apellido sea López.

      ```jsx
      SELECT id, nif, nombre, apellido1, apellido2, id_departamento FROM empleado WHERE apellido2 = 'López';
      +----+-----------+--------+-----------+-----------+-----------------+
      | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
      +----+-----------+--------+-----------+-----------+-----------------+
      |  9 | 56399183D | Juan   | Gómez     | López     |               2 |
      +----+-----------+--------+-----------+-----------+-----------------+
      ```

      

33. Lista todos los datos de los empleados cuyo segundo apellido
          sea Díaz o Moreno. Sin utilizar el operador IN.

      ```jsx
      SELECT id, nif, nombre, apellido1, apellido2, id_departamento FROM empleado WHERE apellido2 = 'Díaz' or apellido2 =  'Moreno';
      +----+-----------+--------+-----------+-----------+-----------------+
      | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
      +----+-----------+--------+-----------+-----------+-----------------+
      |  2 | Y5575632D | Adela  | Salas     | Díaz      |               2 |
      |  6 | 38382980M | María  | Santana   | Moreno    |               1 |
      +----+-----------+--------+-----------+-----------+-----------------+
      ```

      

34. Lista todos los datos de los empleados cuyo segundo apellido
          sea Díaz o Moreno. Utilizando el operador IN.

      ```jsx
      SELECT id, nif, nombre, apellido1, apellido2, id_departamento FROM empleado WHERE apellido2 IN ('Díaz', 'Moreno');
      +----+-----------+--------+-----------+-----------+-----------------+
      | id | nif       | nombre | apellido1 | apellido2 | id_departamento |
      +----+-----------+--------+-----------+-----------+-----------------+
      |  2 | Y5575632D | Adela  | Salas     | Díaz      |               2 |
      |  6 | 38382980M | María  | Santana   | Moreno    |               1 |
      +----+-----------+--------+-----------+-----------+-----------------+
      ```

      

35. Lista los nombres, apellidos y nif de los empleados que trabajan en el
          departamento 3.

      ```jsx
      SELECT nif, nombre, apellido1, apellido2 FROM empleado WHERE id_departamento = 3;
      +-----------+--------+-----------+-----------+
      | nif       | nombre | apellido1 | apellido2 |
      +-----------+--------+-----------+-----------+
      | R6970642B | Adolfo | Rubio     | Flores    |
      | 71651431Z | Pepe   | Ruiz      | Santana   |
      +-----------+--------+-----------+-----------+
      ```

      

36. Lista los nombres, apellidos y nif de los empleados que trabajan en los
      departamentos 2, 4 o 5.

      ```jsx
      SELECT nif, nombre, apellido1, apellido2 FROM empleado WHERE id_departamento IN (2,4,5);
      +-----------+--------+-----------+-----------+
      | nif       | nombre | apellido1 | apellido2 |
      +-----------+--------+-----------+-----------+
      | Y5575632D | Adela  | Salas     | Díaz      |
      | 80576669X | Pilar  | Ruiz      | NULL      |
      | 56399183D | Juan   | Gómez     | López     |
      | 77705545E | Adrián | Suárez    | NULL      |
      | 17087203C | Marcos | Loyola    | Méndez    |
      | 46384486H | Diego  | Flores    | Salas     |
      +-----------+--------+-----------+-----------+
      ```

## Consultas multitabla (Composición interna)

​	Resuelva todas las consultas utilizando la sintaxis de jsx1 y jsx2.

1. Devuelve un listado con los empleados y los datos de los departamentos
    donde trabaja cada uno.

  ```jsx
  SELECT E.nombre as nombre_empleado, E.id_departamento, D.nombre, D.presupuesto, D.gastos
  FROM empleado as E
  INNER JOIN departamento as D ON E.id_departamento=D.id;
  +-----------------+-----------------+------------------+-------------+--------+
  | nombre_empleado | id_departamento | nombre           | presupuesto | gastos |
  +-----------------+-----------------+------------------+-------------+--------+
  | Aarón           |               1 | Desarrollo       |      120000 |   6000 |
  | María           |               1 | Desarrollo       |      120000 |   6000 |
  | Marta           |               1 | Desarrollo       |      120000 |   6000 |
  | Adela           |               2 | Sistemas         |      150000 |  21000 |
  | Pilar           |               2 | Sistemas         |      150000 |  21000 |
  | Juan            |               2 | Sistemas         |      150000 |  21000 |
  | Adolfo          |               3 | Recursos Humanos |      280000 |  25000 |
  | Pepe            |               3 | Recursos Humanos |      280000 |  25000 |
  | Adrián          |               4 | Contabilidad     |      110000 |   3000 |
  | Marcos          |               5 | I+D              |      375000 | 380000 |
  | Diego           |               5 | I+D              |      375000 | 380000 |
  +-----------------+-----------------+------------------+-------------+--------+
  
  ```


2. Devuelve un listado con los empleados y los datos de los departamentos
    donde trabaja cada uno. Ordena el resultado, en primer lugar por el nombre
    del departamento (en orden alfabético) y en segundo lugar por los apellidos
    y el nombre de los empleados.

  ```jsx
  SELECT D.nombre as nombre_departamento, CONCAT( E.apellido1, ' ', E.apellido2) as apellidos_empleado, E.nombre
  FROM empleado as E 
  INNER JOIN departamento as D ON E.id_departamento = D.id ORDER BY D.nombre ASC;
  +---------------------+--------------------+--------+
  | nombre_departamento | apellidos_empleado | nombre |
  +---------------------+--------------------+--------+
  | Contabilidad        | NULL               | Adrián |
  | Desarrollo          | Rivero Gómez       | Aarón  |
  | Desarrollo          | Santana Moreno     | María  |
  | Desarrollo          | Herrera Gil        | Marta  |
  | I+D                 | Loyola Méndez      | Marcos |
  | I+D                 | Flores Salas       | Diego  |
  | Recursos Humanos    | Rubio Flores       | Adolfo |
  | Recursos Humanos    | Ruiz Santana       | Pepe   |
  | Sistemas            | Salas Díaz         | Adela  |
  | Sistemas            | NULL               | Pilar  |
  | Sistemas            | Gómez López        | Juan   |
  +---------------------+--------------------+--------+
  ```

  

3. Devuelve un listado con el identificador y el nombre del departamento,
     solamente de aquellos departamentos que tienen empleados.

     ```jsx
     SELECT D.id, D.nombre
     FROM empleado as E
     INNER JOIN departamento as D ON E.id_departamento = D.id;
     +----+------------------+
     | id | nombre           |
     +----+------------------+
     |  1 | Desarrollo       |
     |  1 | Desarrollo       |
     |  1 | Desarrollo       |
     |  2 | Sistemas         |
     |  2 | Sistemas         |
     |  2 | Sistemas         |
     |  3 | Recursos Humanos |
     |  3 | Recursos Humanos |
     |  4 | Contabilidad     |
     |  5 | I+D              |
     |  5 | I+D              |
     +----+------------------+
     ```

     

4. Devuelve un listado con el identificador, el nombre del departamento y el
     valor del presupuesto actual del que dispone, solamente de aquellos
       departamentos que tienen empleados. El valor del presupuesto actual lo
       puede calcular restando al valor del presupuesto inicial
       (columna presupuesto) el valor de los gastos que ha generado
       (columna gastos).

     ```jsx
     SELECT D.id, D.nombre, ( D.presupuesto - D.gastos) as presupuesto_actual
     FROM empleado as E
     INNER JOIN departamento as D ON E.id_departamento = D.id;
     +----+------------------+--------------------+
     | id | nombre           | presupuesto_actual |
     +----+------------------+--------------------+
     |  1 | Desarrollo       |             114000 |
     |  1 | Desarrollo       |             114000 |
     |  1 | Desarrollo       |             114000 |
     |  2 | Sistemas         |             129000 |
     |  2 | Sistemas         |             129000 |
     |  2 | Sistemas         |             129000 |
     |  3 | Recursos Humanos |             255000 |
     |  3 | Recursos Humanos |             255000 |
     |  4 | Contabilidad     |             107000 |
     |  5 | I+D              |              -5000 |
     |  5 | I+D              |              -5000 |
     +----+------------------+--------------------+
     ```

     

5. Devuelve el nombre del departamento donde trabaja el empleado que tiene
     el nif 38382980M.

     ```jsx
     SELECT D.nombre, E.nombre
     FROM empleado as E
     INNER JOIN departamento as D ON E.id_departamento = D.id WHERE E.nif = '38382980M';
     +------------+--------+
     | nombre     | nombre |
     +------------+--------+
     | Desarrollo | María  |
     +------------+--------+
     ```

     

6. Devuelve el nombre del departamento donde trabaja el empleado Pepe Ruiz
     Santana.

     ```jsx
     SELECT D.nombre, E.nombre
     FROM empleado as E
     INNER JOIN departamento as D ON E.id_departamento = D.id WHERE E.nombre = 'Pepe' AND E.apellido1 = 'Ruiz' AND E.apellido2 = 'Santana';
     +------------------+--------+
     | nombre           | nombre |
     +------------------+--------+
     | Recursos Humanos | Pepe   |
     +------------------+--------+
     ```

     

7. Devuelve un listado con los datos de los empleados que trabajan en el
    departamento de I+D. Ordena el resultado alfabéticamente.

  ```jsx
  SELECT  E.nombre
  FROM empleado as E
  INNER JOIN departamento as D ON E.id_departamento = D.id
  WHERE D.nombre = 'I+D' ORDER BY E.nombre ASC;
  +--------+
  | nombre |
  +--------+
  | Diego  |
  | Marcos |
  +--------+
  ```

  

8. Devuelve un listado con los datos de los empleados que trabajan en el
     departamento de Sistemas, Contabilidad o I+D. Ordena el resultado
       alfabéticamente.

     ```jsx
     SELECT  E.id, E.nombre, E.apellido1, E.apellido2, E.nif
     FROM empleado as E
     INNER JOIN departamento as D ON E.id_departamento = D.id
     WHERE D.nombre IN ('I+D', 'Sistemas', 'Contabilidad') ORDER BY E.nombre ASC;
     +----+--------+-----------+-----------+-----------+
     | id | nombre | apellido1 | apellido2 | nif       |
     +----+--------+-----------+-----------+-----------+
     |  2 | Adela  | Salas     | Díaz      | Y5575632D |
     |  4 | Adrián | Suárez    | NULL      | 77705545E |
     | 10 | Diego  | Flores    | Salas     | 46384486H |
     |  9 | Juan   | Gómez     | López     | 56399183D |
     |  5 | Marcos | Loyola    | Méndez    | 17087203C |
     |  7 | Pilar  | Ruiz      | NULL      | 80576669X |
     +----+--------+-----------+-----------+-----------+
     ```

     

9. Devuelve una lista con el nombre de los empleados que tienen los
     departamentos que no tienen un presupuesto entre 100000 y 200000 euros.

```jsx
SELECT  E.nombre
FROM empleado as E
INNER JOIN departamento as D ON E.id_departamento = D.id
WHERE D.presupuesto NOT BETWEEN 100000  AND 200000;
+--------+
| nombre |
+--------+
| Adolfo |
| Pepe   |
| Marcos |
| Diego  |
+--------+
```

10. Devuelve un listado con el nombre de los departamentos donde existe
    algún empleado cuyo segundo apellido sea NULL. Tenga en cuenta que no
    debe mostrar nombres de departamentos que estén repetidos.

```jsx
SELECT DISTINCT D.nombre
FROM empleado as E
INNER JOIN departamento as D ON E.id_departamento = D.id
WHERE E.apellido2 IS NULL;
+--------------+
| nombre       |
+--------------+
| Contabilidad |
| Sistemas     |
+--------------+

```

## Consultas multitabla (Composición externa)

​	Resuelva todas las consultas utilizando las cláusulas LEFT JOIN y RIGHT JOIN.

1. Devuelve un listado con todos los empleados junto con los datos de los
    departamentos donde trabajan. Este listado también debe incluir los
    empleados que no tienen ningún departamento asociado.

  ```jsx
  SELECT E.nombre, E.apellido1, E.apellido2, D.nombre, D.presupuesto, D.gastos
  FROM empleado as E
  LEFT JOIN departamento as D ON E.id_departamento = D.id;
  +--------------+-----------+-----------+------------------+-------------+--------+
  | nombre       | apellido1 | apellido2 | nombre           | presupuesto | gastos |
  +--------------+-----------+-----------+------------------+-------------+--------+
  | Aarón        | Rivero    | Gómez     | Desarrollo       |      120000 |   6000 |
  | Adela        | Salas     | Díaz      | Sistemas         |      150000 |  21000 |
  | Adolfo       | Rubio     | Flores    | Recursos Humanos |      280000 |  25000 |
  | Adrián       | Suárez    | NULL      | Contabilidad     |      110000 |   3000 |
  | Marcos       | Loyola    | Méndez    | I+D              |      375000 | 380000 |
  | María        | Santana   | Moreno    | Desarrollo       |      120000 |   6000 |
  | Pilar        | Ruiz      | NULL      | Sistemas         |      150000 |  21000 |
  | Pepe         | Ruiz      | Santana   | Recursos Humanos |      280000 |  25000 |
  | Juan         | Gómez     | López     | Sistemas         |      150000 |  21000 |
  | Diego        | Flores    | Salas     | I+D              |      375000 | 380000 |
  | Marta        | Herrera   | Gil       | Desarrollo       |      120000 |   6000 |
  | Irene        | Salas     | Flores    | NULL             |        NULL |   NULL |
  | Juan Antonio | Sáez      | Guerrero  | NULL             |        NULL |   NULL |
  +--------------+-----------+-----------+------------------+-------------+--------+
  ```

  

2. Devuelve un listado donde sólo aparezcan aquellos empleados que no
    tienen ningún departamento asociado.

  ```jsx
  SELECT E.nombre, E.apellido1, E.apellido2, D.nombre AS nombre_departamento, D.presupuesto, D.gastos
  FROM empleado as E
  LEFT JOIN departamento as D ON E.id_departamento = D.id WHERE D.id IS NULL;
  +--------------+-----------+-----------+---------------------+-------------+--------+
  | nombre       | apellido1 | apellido2 | nombre_departamento | presupuesto | gastos |
  +--------------+-----------+-----------+---------------------+-------------+--------+
  | Irene        | Salas     | Flores    | NULL                |        NULL |   NULL |
  | Juan Antonio | Sáez      | Guerrero  | NULL                |        NULL |   NULL |
  +--------------+-----------+-----------+---------------------+-------------+--------+
  ```

  

3. Devuelve un listado donde sólo aparezcan aquellos departamentos que no
    tienen ningún empleado asociado.

  ```jsx
  SELECT D.nombre as nombre_departamento, E.id
  FROM departamento as D
  LEFT JOIN empleado as E ON D.id = E.id_departamento WHERE E.id_departamento IS NULL;
  +---------------------+------+
  | nombre_departamento | id   |
  +---------------------+------+
  | Proyectos           | NULL |
  | Publicidad          | NULL |
  +---------------------+------+
  ```

  

4. Devuelve un listado con todos los empleados junto con los datos de los
    departamentos donde trabajan. El listado debe incluir los empleados que no
    tienen ningún departamento asociado y los departamentos que no tienen
    ningún empleado asociado. Ordene el listado alfabéticamente por el
    nombre del departamento. 

  ```jsx
  SELECT E.id, E.nif, E.nombre, E.apellido1, E.apellido2, E.id_departamento, D.nombre as nombre_departamento
  FROM empleado as E
  LEFT JOIN departamento as D ON E.id_departamento = D.id
  UNION ALL
  SELECT E.id, E.nif, E.nombre, E.apellido1, E.apellido2, E.id_departamento, D.nombre as nombre_departamento
  FROM departamento as D
  LEFT JOIN empleado as E ON E.id_departamento = D.id
  WHERE E.id_departamento IS NULL
  ORDER BY nombre_departamento;
  +------+-----------+--------------+-----------+-----------+-----------------+---------------------+
  | id   | nif       | nombre       | apellido1 | apellido2 | id_departamento | nombre_departamento |
  +------+-----------+--------------+-----------+-----------+-----------------+---------------------+
  |   12 | 41234836R | Irene        | Salas     | Flores    |            NULL | NULL                |
  |   13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |            NULL | NULL                |
  |    4 | 77705545E | Adrián       | Suárez    | NULL      |               4 | Contabilidad        |
  |    1 | 32481596F | Aarón        | Rivero    | Gómez     |               1 | Desarrollo          |
  |    6 | 38382980M | María        | Santana   | Moreno    |               1 | Desarrollo          |
  |   11 | 67389283A | Marta        | Herrera   | Gil       |               1 | Desarrollo          |
  |    5 | 17087203C | Marcos       | Loyola    | Méndez    |               5 | I+D                 |
  |   10 | 46384486H | Diego        | Flores    | Salas     |               5 | I+D                 |
  | NULL | NULL      | NULL         | NULL      | NULL      |            NULL | Proyectos           |
  | NULL | NULL      | NULL         | NULL      | NULL      |            NULL | Publicidad          |
  |    3 | R6970642B | Adolfo       | Rubio     | Flores    |               3 | Recursos Humanos    |
  |    8 | 71651431Z | Pepe         | Ruiz      | Santana   |               3 | Recursos Humanos    |
  |    2 | Y5575632D | Adela        | Salas     | Díaz      |               2 | Sistemas            |
  |    7 | 80576669X | Pilar        | Ruiz      | NULL      |               2 | Sistemas            |
  |    9 | 56399183D | Juan         | Gómez     | López     |               2 | Sistemas            |
  +------+-----------+--------------+-----------+-----------+-----------------+---------------------+
  ```

  

5. Devuelve un listado con los empleados que no tienen ningún departamento
    asociado y los departamentos que no tienen ningún empleado asociado.
    Ordene el listado alfabéticamente por el nombre del departamento. PENDIENTE

  ```jsx
  SELECT  E.id, E.nif, E.nombre, E.apellido1, E.apellido2, E.id_departamento, D.nombre as nombre_departamento
  FROM empleado as E
  LEFT JOIN departamento as D ON E.id_departamento = D.id
  WHERE E.id_departamento IS NULL
  UNION ALL
  SELECT  E.id, E.nif, E.nombre, E.apellido1, E.apellido2, E.id_departamento, D.nombre as nombre_departamento
  FROM departamento as D
  LEFT JOIN empleado as E ON D.id = E.id_departamento
  WHERE E.id_departamento IS NULL
  ORDER BY nombre_departamento;
  +------+-----------+--------------+-----------+-----------+-----------------+---------------------+
  | id   | nif       | nombre       | apellido1 | apellido2 | id_departamento | nombre_departamento |
  +------+-----------+--------------+-----------+-----------+-----------------+---------------------+
  |   12 | 41234836R | Irene        | Salas     | Flores    |            NULL | NULL                |
  |   13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |            NULL | NULL                |
  | NULL | NULL      | NULL         | NULL      | NULL      |            NULL | Proyectos           |
  | NULL | NULL      | NULL         | NULL      | NULL      |            NULL | Publicidad          |
  +------+-----------+--------------+-----------+-----------+-----------------+---------------------+
  ```

  

## Consultas resumen

1. Calcula la suma del presupuesto de todos los departamentos.

   ```jsx
   SELECT  SUM(presupuesto) AS presupuesto_total
   FROM departamento;      
   ```

2. Calcula la media del presupuesto de todos los departamentos.

   ```jsx
   SELECT AVG(presupuesto) as presupuesto_media
   FROM departamento;
   +--------------------+
   | presupuesto_media  |
   +--------------------+
   | 147857.14285714287 |
   +--------------------+
   ```

3. Calcula el valor mínimo del presupuesto de todos los departamentos.

   ```jsx
   SELECT MIN(presupuesto) as presupuesto_minimo
   FROM departamento;
   +-------------------+
   | presupuesto_minimo |
   +-------------------+
   |                 0 |
   +-------------------+
   ```

4. Calcula el nombre del departamento y el presupuesto que tiene asignado,

  del departamento con menor presupuesto.

  ```jsx
  SELECT nombre, presupuesto 
  FROM departamento
  WHERE presupuesto = (SELECT MIN(presupuesto) FROM departamento);
  +------------+-------------+
  | nombre     | presupuesto |
  +------------+-------------+
  | Proyectos  |           0 |
  | Publicidad |           0 |
  +------------+-------------+
  ```


5. Calcula el valor máximo del presupuesto de todos los departamentos.

   ```jsx
   SELECT MAX(presupuesto) as presupuesto_maximo
   FROM departamento;
   +--------------------+
   | presupuesto_maximo |
   +--------------------+
   |             375000 |
   +--------------------+
   ```

6. Calcula el nombre del departamento y el presupuesto que tiene asignado,

  del departamento con mayor presupuesto.

  ```jsx
  SELECT nombre, presupuesto
  FROM departamento
  WHERE presupuesto = (SELECT MAX(presupuesto) FROM departamento);
  +--------+-------------+
  | nombre | presupuesto |
  +--------+-------------+
  | I+D    |      375000 |
  +--------+-------------+
  ```


7. Calcula el número total de empleados que hay en la tabla empleado.

   ```jsx
   SELECT  COUNT(id) as cantidad_empleados FROM empleado;
   +--------------------+
   | cantidad_empleados |
   +--------------------+
   |                 13 |
   +--------------------+
   ```

8. Calcula el número de empleados que no tienen NULL en su segundo
    apellido.

  ```jsx
  SELECT  COUNT(apellido2) as cantidad_apellidos_no_null FROM empleado WHERE apellido1 IS NOT NULL AND apellido2 IS NOT NULL;
  +----------------------------+
  | cantidad_apellidos_no_null |
  +----------------------------+
  |                         11 |
  +----------------------------+
  ```


9. Calcula el número de empleados que hay en cada departamento. Tienes que
    devolver dos columnas, una con el nombre del departamento y otra con el
    número de empleados que tiene asignados.

  ```jsx
  SELECT COUNT(E.id_departamento) AS cantidad, D.nombre as nombre_departamento
  FROM empleado as E
  INNER JOIN departamento as D ON E.id_departamento = D.id
  GROUP BY E.id_departamento
  HAVING COUNT(E.id_departamento) >= 1;
  +----------+---------------------+
  | cantidad | nombre_departamento |
  +----------+---------------------+
  |        3 | Desarrollo          |
  |        3 | Sistemas            |
  |        2 | Recursos Humanos    |
  |        1 | Contabilidad        |
  |        2 | I+D                 |
  +----------+---------------------+
  ```


10. Calcula el nombre de los departamentos que tienen más de 2 empleados. El
    resultado debe tener dos columnas, una con el nombre del departamento y
    otra con el número de empleados que tiene asignados.

    ```jsx
    SELECT D.nombre as nombre_departamento, COUNT(E.id_departamento) as cantidad 
    FROM empleado as E
    INNER JOIN departamento as D ON E.id_departamento = D.id
    GROUP BY E.id_departamento
    HAVING COUNT(E.id_departamento) > 2;
    +---------------------+----------+
    | nombre_departamento | cantidad |
    +---------------------+----------+
    | Desarrollo          |        3 |
    | Sistemas            |        3 |
    +---------------------+----------+
    ```

11. Calcula el número de empleados que trabajan en cada uno de los
    departamentos. El resultado de esta consulta también tiene que incluir
    aquellos departamentos que no tienen ningún empleado asociado.

    ```jsx
    SELECT D.nombre AS nombre_departamento, COUNT(E.id) AS cantidad_empleados
    FROM departamento AS D
    LEFT JOIN empleado AS E ON D.id = E.id_departamento
    GROUP BY D.nombre;
    ```
    
12. Calcula el número de empleados que trabajan en cada unos de los
    departamentos que tienen un presupuesto mayor a 200000 euros.

    ```jsx
    SELECT D.nombre AS nombre_departamento, COUNT(E.id) AS cantidad_empleados
    FROM departamento AS D
    LEFT JOIN empleado AS E ON D.id = E.id_departamento
    WHERE D.presupuesto > 200000 
    GROUP BY D.nombre;
    +---------------------+--------------------+
    | nombre_departamento | cantidad_empleados |
    +---------------------+--------------------+
    | Recursos Humanos    |                  2 |
    | I+D                 |                  2 |
    +---------------------+--------------------+
    ```
    
    ## Subconsultas
    
    Con operadores básicos de comparación
    
    1. Devuelve un listado con todos los empleados que tiene el departamento
        de Sistemas. (Sin utilizar INNER JOIN).
    
      ```jsx
      SELECT E.id, E.nombre, E.apellido1, E.apellido2 
      FROM empleado as E, departamento as D
      WHERE E.id_departamento = D.id AND D.nombre = 'Sistemas'
      +----+--------+-----------+-----------+
      | id | nombre | apellido1 | apellido2 |
      +----+--------+-----------+-----------+
      |  2 | Adela  | Salas     | Díaz      |
      |  7 | Pilar  | Ruiz      | NULL      |
      |  9 | Juan   | Gómez     | López     |
      +----+--------+-----------+-----------+
      ```
    
    
    2. Devuelve el nombre del departamento con mayor presupuesto y la cantidad
        que tiene asignada.
    
      ```jsx
      SELECT D.nombre, presupuesto
      FROM departamento as D
      WHERE presupuesto = (SELECT MAX(presupuesto) FROM departamento);
      +--------+-------------+
      | nombre | presupuesto |
      +--------+-------------+
      | I+D    |      375000 |
      +--------+-------------+
      ```
    
      
    
    3. Devuelve el nombre del departamento con menor presupuesto y la cantidad
        que tiene asignada.
        Subconsultas con ALL y ANY
    
      ```jsx
      SELECT D.nombre, presupuesto 
      FROM departamento as D
      WHERE presupuesto = (SELECT MIN(presupuesto) FROM departamento)
      LIMIT 1;
      +-----------+-------------+
      | nombre    | presupuesto |
      +-----------+-------------+
      | Proyectos |           0 |
      +-----------+-------------+
      
      ```
    
      
    
    4. Devuelve el nombre del departamento con mayor presupuesto y la cantidad
        que tiene asignada. Sin hacer uso de MAX, ORDER BY ni LIMIT.
    
      ```jsx
      SELECT D.nombre, D.presupuesto
      FROM departamento as D
      ORDER BY D.presupuesto DESC
      LIMIT 1;
      +--------+-------------+
      | nombre | presupuesto |
      +--------+-------------+
      | I+D    |      375000 |
      +--------+-------------+
      ```
    
      
    
    5. Devuelve el nombre del departamento con menor presupuesto y la cantidad
        que tiene asignada. Sin hacer uso de MIN, ORDER BY ni LIMIT.
    
      ```jsx
      SELECT D.nombre, D.presupuesto
      FROM departamento as D 
      ORDER BY D.presupuesto 
      LIMIT 1;
      +-----------+-------------+
      | nombre    | presupuesto |
      +-----------+-------------+
      | Proyectos |           0 |
      +-----------+-------------+
      ```
    
      
    
    6. Devuelve los nombres de los departamentos que tienen empleados
        asociados. (Utilizando ALL o ANY).
    
      ```jsx
      SELECT nombre
      FROM departamento
      WHERE id = ANY (SELECT id_departamento FROM empleado);
      +------------------+
      | nombre           |
      +------------------+
      | Desarrollo       |
      | Sistemas         |
      | Recursos Humanos |
      | Contabilidad     |
      | I+D              |
      +------------------+
      ```
    
      
    
    7. Devuelve los nombres de los departamentos que no tienen empleados
        asociados. (Utilizando ALL o ANY).
        Subconsultas con IN y NOT IN
    
      ```jsx
      SELECT D.nombre
      FROM departamento as D
      WHERE D.id NOT IN (SELECT id_departamento FROM empleado);
      ```
    
      
    
    8. Devuelve los nombres de los departamentos que tienen empleados
        asociados. (Utilizando IN o NOT IN).
    
      ```jsx
      SELECT D.nombre
      FROM departamento as D
      WHERE D.id IN (SELECT id_departamento FROM empleado);
      +------------------+
      | nombre           |
      +------------------+
      | Desarrollo       |
      | Sistemas         |
      | Recursos Humanos |
      | Contabilidad     |
      | I+D              |
      +------------------+
      ```
    
      
    
    9. Devuelve los nombres de los departamentos que no tienen empleados
        asociados. (Utilizando IN o NOT IN).
        Subconsultas con EXISTS y NOT EXISTS
    
      ```
      SELECT D.nombre
      FROM departamento as D
      WHERE D.id NOT IN (SELECT id_departamento FROM empleado);
      ```
    
      
    
    10. Devuelve los nombres de los departamentos que tienen empleados
        asociados. (Utilizando EXISTS o NOT EXISTS).
    
        ```jsx
        SELECT nombre
        FROM departamento AS D
        WHERE EXISTS (
            SELECT 1
            FROM empleado AS E
            WHERE E.id_departamento = D.id
        );
        +------------------+
        | nombre           |
        +------------------+
        | Desarrollo       |
        | Sistemas         |
        | Recursos Humanos |
        | Contabilidad     |
        | I+D              |
        +------------------+
        
        ```
    
        
    
    11. Devuelve los nombres de los departamentos que tienen empleados
        asociados. (Utilizando EXISTS o NOT EXISTS).
    
        ```
        SELECT nombre
        FROM departamento AS D
        WHERE EXISTS (
            SELECT 1
            FROM empleado AS E
            WHERE E.id_departamento = D.id
        );
        +------------------+
        | nombre           |
        +------------------+
        | Desarrollo       |
        | Sistemas         |
        | Recursos Humanos |
        | Contabilidad     |
        | I+D              |
        +------------------+
        x|
        ```
    
        #   c o n s u l t a s S Q L _ 2 
         
         