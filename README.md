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
