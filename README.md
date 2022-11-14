 <p align="left">
   <img src="https://img.shields.io/badge/status-en%20desarrollo-green"> 
   <img src="https://img.shields.io/github/issues/jesusdanielquiroga/model-api">
   <img src="https://img.shields.io/github/forks/jesusdanielquiroga/model-api">
   <img src="https://img.shields.io/github/forks/jesusdanielquiroga/model-api">
   <img src="https://img.shields.io/github/license/jesusdanielquiroga/model-api">
<a href="https://twitter.com/intent/tweet?text=Wow:&url=https%3A%2F%2Fgithub.com%2Fjesusdanielquiroga%2FIntroduccion-Base-de-Datos"><img alt="Twitter" src="https://img.shields.io/twitter/url?style=social&url=https%3A%2F%2Ftwitter.com%2Fjdquiroga2410"></a>
   <img src="https://img.shields.io/github/stars/camilafernanda?style=social">
   <img src="https://img.shields.io/badge/topic-basededatos-green">
  </p>

 ![Banner de LinkedIn Trabajo Sencillo](https://user-images.githubusercontent.com/87950040/200203775-86f6257d-7eaf-4ad9-b5c2-2a818581ac18.png)

  <h1 align="left"> Introducción Base de Datos </h1>
  
 Repositorio de la formación sobre base de datos.
 
 ## Índice

* [Índice](#índice)

* [Introducción](#introducción)

* [Definición](#definición)

* [Historia de las RDB (relational data bases)](#historia-de-las-rdb)

* [Entidades y atributos](#entidades-y-atributos)

* [Relaciones](#relaciones)

* [Diagrama Entidad Relación](#diagrama-entidad-relación)

* [Tipos de datos y constraints](#tipos-de-datos-y-constraints)

* [Normalización](#normalización)

* [SQL](#sql)

* [Tablas](#tablas)

* [Importancia de las consultas](#importancia-de-las-consultas)

* [Estructura básica de un query](#estructura-básica-de-un-query)

# Introducción

El objetivo principal de las bases de datos es el de unificar los datos que se manejan y los programas o aplicaciones que los manejan. Anteriormente los programas se codificaban junto con los datos, es decir, se diseñaban para la aplicación concreta que los iba a manejar, lo que desembocaba en una dependencia de los programas respecto a los datos, ya que la estructura de los ficheros va incluida dentro del programa, y cualquier cambio en la estructura del fichero provocaba modificar y
recompilar programas. Además, cada aplicación utiliza ficheros que pueden ser comunes a otras de la misma organización, por lo que se produce una REDUNDANCIA de la información, que provoca mayor ocupación de memoria, laboriosos programas de actualización (unificar datos recogidos por las aplicaciones de los diferentes departamentos), e inconsistencia de datos (no son correctos) si los datos no fueron bien actualizados en todos los programas. Con las bases de datos, se busca
independizar los datos y las aplicaciones, es decir, mantenerlos en espacios diferentes. Los datos residen en memoria y los programas mediante un sistema gestor de bases de datos, manipulan la información. El sistema gestor de bases de datos recibe la petición por parte del programa para manipular los datos y es el encargado de recuperar la información de la base de datos y devolvérsela al programa que la solicitó. Cada programa requerirá de una cierta información de la base de datos, y
podrá haber otros que utilicen los mismos datos, pero realmente residirán en el mismo espacio de almacenamiento y los programas no duplicarán esos datos, si no que trabajarán directamente sobre ellos concurrentemente. Aunque la estructura de la base de datos cambiara, si los datos modificados no afectan a un programa específico, éste no tendrá por qué ser alterado. Mediante estas técnicas de base de datos se pretende conseguir a través del **Sistema Gestor de Bases de Datos(SGBD)**:

* INDEPENDENCIA de los Datos: Cambios en la estructura de la Base de Datos no modifican las aplicaciones. 
* INTEGRIDAD de los Datos: Los datos han de ser siempre correctos. Se establecen una serie de restricciones (reglas de validación) sobre los datos.
* SEGURIDAD de los Datos: Control de acceso a los datos para evitar manipulaciones de estos no deseadas. 

# Definición 

Es una colección de datos referentes a una organización estructurada según un modelo de datos de forma que refleja las relaciones y restricciones existentes entre los objetos del mundo real, y consigue independencia, integridad y seguridad de los datos. 

Lo que debemos tener claro es la diferencia entre **Base de Datos** y **SGBD**. La **base de datos** es el almacenamiento donde residen los datos. El SGBD es el encargado de manipular la información contenida en ese almacenamiento mediante operaciones de lectura/escritura sobre la misma. Además las bases de datos no sólo contendrán las tablas (ficheros) de datos, sino que también almacenará formularios (interfaces para edición de datos), consultas sobre los datos, e informes. El **SGBD** se encargará de manipular esos datos, controlar la integridad y seguridad de los datos, reconstruir y reestructurar la base de datos cuando sea necesario. 

# Historia de las RDB

Las bases de datos surgen de la necesidad de conservar la información más allá de lo que existe en la memoria RAM.

Las bases de datos basadas en archivos eran datos guardados en texto plano, fáciles de guardar pero muy difíciles de consultar y por la necesidad de mejorar esto nacen las bases de datos relacionales. Su inventor **Edgar Codd** dejó ciertas reglas para asegurarse de que toda la filosofía de las bases de datos no se perdiera, estandarizando el proceso, Codd invento el algebra relacional

**(Contenido adicional) Bases de datos relacionales (RBD)**

Es importante que sea fácil de guardar y extraer, anteriormente se usaban bases de datos basadas en archivos, el cuál era texto plano fácil de guardar, pero difícil de extraer, por esto se inventaron las bases de datos relacionales. En 1990 Codd se preocupó porque los **sistemas de gestión de bases de datos (SGBD)** que decían ser relacionales, no lo eran. En la práctica es difícil cumplir las 12 pero, un SGBD es más relacional cuantas más reglas cumpla

**Las Reglas y mandamientos de Edgar Frank Ted Codd**

**Regla 0**: Regla de fundación. a) Cualquier sistema que se proclame como relacional, debe ser capaz de gestionar sus bases de datos enteramente mediante sus capacidades relacionales.

**Regla 1**: Regla de la información. a) Todos los datos deben estar almacenados en las tablas b) Esas tablas deben cumplir las premisas del modelo relacional c) No puede haber información a la que accedemos por otra vía

**Regla 2**: Regla del acceso garantizado. a) Cualquier dato es accesible sabiendo la clave de su fila y el nombre de su columna o atributo b) Si a un dato no podemos acceder de esta forma, no estamos usando un modelo relacional

**Regla 3**: Regla del tratamiento sistemático de valores nulos. a) Esos valores pueden dar significado a la columna que los contiene b) El SGBD debe tener la capacidad de manejar valores nulos c) El SGBD reconocerá este valor diferenciándolo de cualquier otro d) El SGBD deberá aplicársele la lógica apropiada e) Es un valor independiente del tipo de datos de la columna

**Regla 4**: Catálogo dinámico en línea basado en el modelo relacional. a) El catálogo en línea es el diccionario de datos b) El diccionario de datos se debe de poder consultar usando las mismas técnicas que para los datos c) Los metadatos, por tanto, se organizan también en tablas relacionales d) Si SELECT es una instrucción que consulta datos, también será la que consulta los metadatos

**Regla 5**: Regla comprensiva del sublenguaje de los datos completo. a) Al menos tiene que existir un lenguaje capaz de hacer todas las funciones del SGBD b) No puede haber funciones fuera de ese lenguaje c) Puede haber otros lenguajes en el SGBD para hacer ciertas tareas d) Pero esas tareas también se deben poder hacer con el “lenguaje completo”

**Regla 6**: Regla de actualización de vistas. a) Las vistas tienen que mostrar información actualizada b) No puede haber diferencias entre los datos de las vistas y los datos de las tablas base

**Regla 7**: Alto nivel de inserción, actualización, y cancelación. a) La idea es que el lenguaje que maneja la base de datos sea muy humano b) Eso implica que las operaciones del lenguaje de manipulación de los datos (DML) trabajen con conjuntos de filas a la vez c) Para modificar, eliminar o añadir datos, no hará falta programar de la forma en la que lo hacen los lenguajes de tercera generación como C o Java

**Regla 8**: Independencia física de los datos. a) Cambios en la física de la BD no afecta a las aplicaciones ni a los esquemas lógicos b) El acceso a las tablas (elemento lógico) no cambia porque la física de la base de datos cambie

**Regla 9**: Independencias lógicas de los datos. a) Cambios en el esquema lógico (tablas) de la BD no afectan al resto de esquemas b) Si cambiamos nombres de tabla, o de columna o modificamos información de las filas, las aplicaciones (esquema externo) no se ven afectadas c) Es más difícil de conseguir

**Regla 10**: Independencia de la integridad. a) Las reglas de integridad (restricciones) deben de ser gestionadas y almacenadas por el SGBD

**Regla 11**: Independencia de la distribución. a) Que la base de datos se almacene o gestione de forma distribuida en varios servidores, no afecta al uso de esta ni a la programación de las aplicaciones de usuario b) El esquema lógico es el mismo independientemente de si la BD es distribuida o no

**Regla 12**: La regla de la no subversión. a) La base de datos no permitirá que exista un lenguaje o forma de acceso, que permita saltarse las reglas anteriores.

# Entidades y atributos

Una **entidad** es algo similar a un objeto (programación orientada a objetos) y representa algo en el mundo real, incluso algo abstracto. Tienen atributos que son las cosas que los hacen ser una entidad, se diagraman dentro de cuadrados y por convención se ponen en plural.

Entidad Fuerte: No depende de ninguna entidad para existir

Entidades débiles: No pueden existir sin una entidad fuerte y se representan con un cuadrado con doble línea.

* Identidades débiles por identidad: No se diferencian entre sí más que por la clave de su identidad fuerte.
* Identidades débiles por existencia: Se les asigna una clave propia.

Los **atributos** se representan con óvalos, los que tienen multiples valores llevan dobles óvalos, también existen atributos compuestos, los atributos especiales son óvalos con linea punteada.

Los atributos compuestos son aquellos que tienen atributos ellos mismos.

Los atributos llave son aquellos que identifican a la entidad y no pueden ser repetidos, se diagraman con underline. Existen:

* Naturales: Son inherentes al objeto como el número de serie
* Clave artificial: No es inherente al objeto y se asigna de manera arbitraria

# Relaciones

Las relaciones nos permiten ligar o unir nuestras diferentes entidades y se representan con rombos. Por convención se definen a través de verbos.

Las relaciones tienen una propiedad llamada cardinalidad y tiene que ver con números. Cuántos de un lado pertenecen a cuántos del otro lado:

* Cardinalidad: 1 a 1 

![cardinalidad](https://user-images.githubusercontent.com/87950040/200440474-78e62912-3032-49cb-a5b6-69a8206597fe.JPG)

* Cardinalidad: 0 a 1 

![cardinalidad](https://user-images.githubusercontent.com/87950040/200440608-c5d433e4-f008-4628-a8eb-6578f20547be.JPG)

* Cardinalidad: 1 a N 

![cardinalidad](https://user-images.githubusercontent.com/87950040/200440725-287fe43c-1ed6-49c2-9ca3-1f1fd1652066.JPG)

* Cardinalidad: 0 a N

![cardinalidad](https://user-images.githubusercontent.com/87950040/200440858-0add4255-d6a9-479f-9834-7af54c25fdf5.JPG)

# Diagrama Entidad Relación

Un diagrama es como un mapa y nos ayuda a entender cuáles son las entidades con las que vamos a trabajar, cuáles son sus relaciones y qué papel van a jugar en las aplicaciones de la base de datos.

![cardinalidad](https://user-images.githubusercontent.com/87950040/200441668-055de8f8-e1d1-4df0-ab76-70b2c0f3d414.JPG)

# Tipos de datos y constraints

**Tipos de dato**

* Texto:
CHAR(n), VARCHAR(n), TEXT 

* Números:
INTEGER, BIGINT, SMALLINT, DECIMAL(n,s), NUMERIC(n,s)

* Fecha/hora:
DATE, TIME, DATETIME, TIMESTAMP

* Lógicos: 
BOOLEAN

**Nota:**
Char(8) reserva 8 espacios en memoria de forma fija, Varchar(8) hace lo mismo pero crece (1,2,3...8) de manera dinámica conforme los requieres y tiene un limite general de 255 caracteres.

**Constraints (Restricciones)**

* NOT NULL: Se asegura que la columna no tenga valores nulos - UNIQUE: Se asegura que cada valor en la columna no se repita
* PRIMARY KEY: Es una combinación de NOT NULL y UNIQUE - FOREIGN KEY: Identifica de manera única una tupla en otra tabla
* CHECK: Se asegura que el valor en la columna cumpla una condición dada
* DEFAULT: Coloca un valor por defecto cuando no hay un valor especificado
* INDEX: Se crea por columna para permitir búsquedas más rápidas, tiene la desventaja de que tiene que reindexar los registros cada vez, lo que vuelve muy lenta la operación de la bd.

# Normalización

La normalización como su nombre lo indica nos ayuda a dejar todo de una forma normal. Esto obedece a las 12 reglas de Codd y nos permiten separar componentes en la base de datos:

**Primera Forma Normal (1FN)**

Esta FN nos ayuda a eliminar los valores repetidos y no atómicos dentro de una base de datos.

Formalmente, una tabla está en primera forma normal si:

* Todos los atributos son atómicos. Un atributo es atómico si los elementos del dominio son simples e indivisibles.
* No debe existir variación en el número de columnas.
* Los campos no clave deben identificarse por la clave (dependencia funcional).
* Debe existir una independencia del orden tanto de las filas como de las columnas; es decir, si los datos cambian de orden no deben cambiar sus significados.
* Se traduce básicamente a que si tenemos campos compuestos como por ejemplo “nombre_completo” que en realidad contiene varios datos distintos, en este caso podría ser “nombre”, “apellido_paterno”, “apellido_materno”, etc.

Se traduce básicamente a que si tenemos campos compuestos como por ejemplo “nombre_completo” que en realidad contiene varios datos distintos, en este caso podría ser “nombre”, “apellido_paterno”, “apellido_materno”, etc.

Los campos deben ser tales que si reordenamos los registros o reordenamos las columnas, cada dato no pierda el significado.

**Segunda Forma Normal (2FN)**

Esta FN nos ayuda a diferenciar los datos en diversas entidades.

Formalmente, una tabla está en segunda forma normal si:

* Está en 1FN
* Sí los atributos que no forman parte de ninguna clave dependen de forma completa de la clave principal. Es decir, que no existen dependencias parciales.
* Todos los atributos que no son clave principal deben depender únicamente de la clave principal.

Lo anterior quiere decir que sí tenemos datos que pertenecen a diversas entidades, cada entidad debe tener un campo clave separado.

**Tercera Forma Normal (3FN)**

Esta FN nos ayuda a separar conceptualmente las entidades que no son dependientes.

Formalmente, una tabla está en tercera forma normal si:

Se encuentra en 2FN No existe ninguna dependencia funcional transitiva en los atributos que no son clave

Esta FN se traduce en que aquellos datos que no pertenecen a la entidad deben tener una independencia de las demás y debe tener un campo clave propio. 

**Cuarta Forma Normal (4FN)**

Esta FN nos trata de atomizar los datos multivaluados de manera que no tengamos datos repetidos entre rows.

Formalmente, una tabla está en cuarta forma normal si:

* Se encuentra en 3FN
* Los campos multivaluados se identifican por una clave única

Esta FN trata de eliminar registros duplicados en una entidad, es decir que cada registro tenga un contenido único y de necesitar repetir la data en los resultados se realiza a través de claves foráneas.

De esta manera, aunque parezca que la información se multiplicó, en realidad la descompusimos o normalizamos de manera que a un sistema le sea fácil de reconocer y mantener la consistencia de los datos.

Algunos autores precisan una 5FN que hace referencia a que después de realizar esta normalización a través de uniones (JOIN) permita regresar a la data original de la cual partió.

# SQL

SQL significa Structured Query Language y tiene una estructura clara y fija. Su objetivo es hacer un solo lenguaje para consultar cualquier manejador de bases de datos volviéndose un gran estándar.

Ahora existe el NOSQL o Not Only Structured Query Language que significa que no sólo se utiliza SQLen las bases de datos no relacionales.

SQL tiene dos grandes sublenguajes DDL y DML.

## DDL

DDL o Data Definition Language que nos ayuda a crear la estructura de una base de datos. Existen 3 grandes comandos:

* Create: Nos ayuda a crear bases de datos, tablas, vistas, índices, etc.

* Alter: Ayuda a alterar o modificar entidades.

* Drop: Nos ayuda a borrar. Hay que tener cuidado al utilizarlo.

3 objetos que manipularemos con el lenguaje DDL:

* Database o bases de datos
* Table o tablas: Son la traducción a SQL de las entidades
* View o vistas: Se ofrece la proyección de los datos de la base de datos de forma entendible.

**CREATE**

```sh

CREATE DATABASE tiendas_aby;
USE DATABASE tiendas_aby;

------------------------------------------------

CREATE TABLE people (
	person_id int,
	last_name varchar(255),
	first_name varchar(255),
	address varchar(255),
	city varchar(255) 
);

------------------------------------------------

CREATE VIEW v_brasil_customers AS
    SELECT customer_name, contact_name
    FROM customers
    WHERE country = "Brasil";
    
```

**ALTER**

```sh

ALTER TABLE people
ADD date_of_birth date;

------------------------------------------------

ALTER TABLE people
ALTER COLUMN date_of_birth year;

------------------------------------------------

ALTER TABLE people
DROP COLUMN date_of_birth;
    
```

**DROP**

```sh

DROP TABLE people
DROP DATABASE tiendas_aby;
  
```

## DML

Trata del contenido de la base de datos. Data Manipulation Language.

```sh
-- Insert
INSERT INTO people (last_name, first_name, address, city)
VALUES ('Hernández', 'Laura', 'Calle 21', 'Monterrey');

-- Update
UPDATE people
SET last_name = 'Chávez', city= 'Mérida'
WHERE person_id = 1;

UPDATE people
SET first_name = 'Juan'
WHERE city = 'Mérida';

UPDATE people
SET first_name = 'Juan';

-- Delete
DELETE FROM people 
WHERE person_id = 1;

DELETE FROM people;

-- Select
SELECT fist_name, last_name FROM people;
```

# Tablas

## Tablas Independientes

Son entidades que no tienen una llave foránea, es una buena práctica comenzar la BD por ellas. 

## Tablas Dependientes

Son entidades que dependen de otra o estan relacionadas con una llave foránea:

```sh
ALTER TABLE `platziblog`.`posts` 
ADD INDEX `post_usuarios_idx` (`usuario_id` ASC) ;

ALTER TABLE `platziblog`.`posts` 
ADD CONSTRAINT `post_usuarios`
  FOREIGN KEY (`usuario_id`)
  REFERENCES `platziblog`.`usuarios` (`id`)
  ON DELETE NO ACTION
  ON UPDATE CASCADE;
```
Una llave foránea se crea en la pestaña foreing key. Las Foreing Key options son las siguientes:

* **On update**: Significa qué pasará con las relaciones cuando una de estas sea modificada en sus campos relacionados, Por ejemplo, pueden utilizarse los valores:
cascade: Si el id de un usuario pasa de 11 a 12, entonces la relacion se actualizará y el post buscará el id nuevo en lugar de quedarse sin usuario.
* **_restrict**: Si el id de un usuario pasa de 11 a 12, no lo permitirá hasta que no sean actualizados antes todos los post relacionados.
set null Si el id de un usuario pasa de 11 a 12, entonces los post solo no estará relacionados con nada.
no action: Si el id de un usuario pasa de 11 a 12, no se hará nada. Solo se romperá la relación.
* **cascade**: Si un usuario es eliminado entonces se borrarán todos los post relacionados.
* **set null**: Si un usuario es eliminado, entonces los post solo no estará relacionados con nada.
no action: Si un usuario es eliminado, no se hará nada. Solo se romperá la relación.

## Tablas Transitivas

Sirven como puente para unir dos tablas. Estas no contiene contenido semantico. 

## Reverse Engineer 

Es una herramienta que nos permite generar el esquema del cual nos basamos para crear nuestras tablas. Es muy útil para conocer como se creo una base de datos.

<img width="485" alt="engineer rev" src="https://user-images.githubusercontent.com/87950040/201502367-cd5998b3-5575-4937-b9a4-c5a9ec6801ed.png">

Genera el modelo DB: 

<img width="473" alt="engineer model" src="https://user-images.githubusercontent.com/87950040/201502447-072dd88b-4a10-45b0-8c18-81897e9a066f.png">


# Importancia de las consultas

Las consultas en una base de datos juegan un papel muy fundamental, puesto que facilitan de manera considerable los procesos en cualquier empresa.
## ETL
La palabra ETL correspondería al acrónimo de:
* Extract (Extraer)
* Transform (Transformar)
* Load (Cargar)

ETL hace parte del proceso de integración de datos, mas aun es un componente muy importante que completa el resultado final en la relación de aplicaciones y sistemas.

# Estructura básica de un query

Los query son la forma en la que se estructura las preguntas que se hacen a la base de datos. Transforma preguntas en sintaxis. Los query básicamente tienen dos partes **SELECT** y **FROM**.

* **SELECT**: que datos queremos obtener (que columnas/campos de la tabla).
* **FROM** : de donde los queremos obtener (de que tabla, por ejemplo).
* **WHERE** : condicion que deben cumplir o filtro que deben pasar los datos a obtener. Es opcional, pero se suele utilizar, ya que sino se obtienen todos los datos sin filtrar ninguno.
* 
Otras sentencias:
* **GROUP BY** : de que manera agrupamos los datos (en este caso agrupa por ciudad).
* **ORDER BY** : de que manera ordenamos los datos (en este caso, por poblacion).
* **HAVING** : otra manera de filtrar los datos.
```SH
-- Estructura basica de un query
SELECT	*
FROM		posts;

-- Estructura extendida de un query
SELECT	*
FROM		posts
WHERE	fecha_publicacion > '2024-00-00 00:00:00';
```
```SH
(*) Indica dentro de la consulta que vamos a seleccionar todo sin filtrar campos
```
## SELECT

Es la primera parte de la estructura que necesitamos para hacer preguntas a la base de datos. Se encarga de proyectar o mostrar los datos que le pedimos a la base de datos.
```sh
SELECT	*
FROM	posts;
```
Si escribimos "SELECT " y luego uno o varios nombres de los campos de la tabla, separados por coma, unicamente recibiremos dichos los datos de dichas columnas.
```sh
SELECT	titulo, fecha_publicacion, estatus
FROM   posts;
```
Por cada campo, podemos agregar un “_AS _ …” (por ejemplo, " titulo AS encabezado ). Esto nos permitira mostrar las columnas con un nombre diferente: en este caso mostrara la columna titulo con el nombre encabezado.

```sh
SELECT	titulo AS encabezado, 
fecha_publicacion AS publicado, 
estatus AS estado
FROM 	posts;
```
También puedes generar encabezados con espacios encerrando el nombre entre apostrofes, por ejemplo:
```sh
SELECT titulo AS encabezado,
fecha_publicacion AS 'publicado en’,
estatus AS estado
FROM 	posts;
```

Si indicamos " SELECT COUNT (*)", la funcion COUNT contara todas las filas de la tabla (usualmente se usa con algun filtro, para no elegir todas las columnas de la tabla).
```sh
SELECT	count(*)
FROM		posts;
--------------------------------------------------
SELECT	count(*) AS numero_posts
FROM		posts;
```
## FROM

Indica de dónde se deben traer los datos y puede ayudar a hacer sentencias y filtros complejos cuando se quieren unir tablas. La sentencia compañera que nos ayuda con este proceso es **JOIN**.

## JOIN

Esta sentencia esta relacionada con la Teoría de Conjuntos, donde se utilizan los **diagramas de Venn**, que son círculos que se tocan en algún punto para ver dónde está la intersección de conjuntos. Ayudan mucho para poder formular la sentencia JOIN de la manera adecuada dependiendo del query que se quiere hacer.

![sqljoin](https://user-images.githubusercontent.com/87950040/201504653-4d977c91-c5ef-4d01-ae9e-f0366444b4a6.jpeg)


1. Diferencia:
* LEFT Join (Con la intersección): Trae todo los datos de la tabla A, que estén o no estén de la tabla B.
```sh
SELECT	*
FROM	usuarios 
	LEFT JOIN posts on usuarios.id = posts.usuario_id;
```
* LEFT JOIN (Sin la intersección): Trae todo los datos de la tabla A, que no estén en la tabla B.
```sh
SELECT	*
FROM	usuarios 
	LEFT JOIN posts on usuarios.id = posts.usuario_id
WHERE	posts.usuario_id IS NULL;
```
* RIGHT JOIN(Con la intersección): Trae todo los datos de la tabla B, que estén o no estén de la tabla A.
```sh
SELECT	*
FROM	usuarios 
	RIGHT JOIN posts on usuarios.id = posts.usuario_id;
```
* RIGHT JOIN(Sin la intersección):Trae todo los datos de la tabla B, que no estén en la tabla A.
```sh
SELECT	*
FROM	usuarios 
	RIGHT JOIN posts on usuarios.id = posts.usuario_id
WHERE	posts.usuario_id IS NULL;
```

2. Intersección:

* INNER JOIN: Solo arrastra valores que estén tanto en la Tabla A como en la Tabla B.
```sh
SELECT	*
FROM	usuarios 
	INNER JOIN posts on usuarios.id = posts.usuario_id;
```
3. Unión y Diferencia Simétrica__
* UNION: Trae todo de la tabla A y Tabla B. (Unión)
```sh
SELECT	*
FROM		usuarios 
	LEFT JOIN posts   ON usuarios.id = posts.usuario_id
UNION 
SELECT	*
FROM		usuarios 
	RIGHT JOIN posts ON usuarios.id = posts.usuario_id;
```
* OUTER JOIN: Trae todo de la tabla A y B; pero solo información que no guarde relación una tabla con la otra. (Diferencia Simétrica)
```sh
SELECT	*
FROM	usuarios 
	LEFT JOIN posts on usuarios.id = posts.usuario_id
WHERE	posts.usuario_id IS NULL
UNION
SELECT	*
FROM	usuarios 
	RIGHT JOIN posts on usuarios.id = posts.usuario_id
WHERE	posts.usuario_id IS NULL;
```
## WHERE

Nos ayuda a filtrar registros (filas de la tabla). Podemos filtrar por ejemplo, a partir de cierto numero de ID (con el operador de mayor o menor).
```sh
SELECT	*
FROM		posts
WHERE	id	< 50;
```
**LIKE**: cuando no conocemos la cadena exacta. Podemos filtrar segun alguna caracteristica. Por ejemplo:
WHERE titulo LIKE ‘%escandalo%’ lo que hace es buscar aquellos titulos que tengan la palabra escandalo en alguna parte. Sin embargo, como los signos porcentuales indican que hay algo mas, si quitamos, por ejemplo, el del final (quedando ‘%escandalo’), estaremos buscando aquellos titulos que terminen con la palabra ‘escandalo’, ya que indicamos que despues de esta palabra no hay nada mas.
```sh
SELECT	*
FROM		posts
WHERE	titulo LIKE '%escandalo%';
```
**BETWEEN**: la traduccion de esta palabra al español es ‘entre’. Por lo tanto, como podemos imaginar, filtrara entre dos valores a designar. Por ejemplo:
WHERE fechaDePublicacion BETWEEN ‘2019-01-01’ AND ‘2019-01-10’ filtrara las publicaciones con fecha de publicacion entre el 1 de enero de 2019 y 10 de enero de 2019. Puede utilizarse tambien con valores numericos (y por lo tanto, por ejemplo, con los IDs).

```sh
SELECT	*
FROM		posts
WHERE	fecha_publicacion BETWEEN '2023-01-01' AND '2025-12-31';
```

## GROUP BY

La instruccion GROUP BY, agrupa las filas que tienen los mismos valores en filas de resumen, como por ejemplo saber cuantas personas han comprado un producto.
El GROUP BY se utiliza a menudo con funciones de agregado (COUNT(), MAX(), MIN(), SUM(), AVG())

```sh
SELECT nombre_columna(s)
FROM nombre_tabla(s)
WHERE condicion
GROUP BY nombre_columna(s)
```
```sh
SELECT	estatus, MONTHNAME(fecha_publicacion) AS post_date, COUNT(*) AS post_number
FROM		posts
GROUP BY estatus, post_date;
```
