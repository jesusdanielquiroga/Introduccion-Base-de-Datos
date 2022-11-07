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

# Introducción

El objetivo principal de las bases de datos es el de unificar los datos que se manejan y los programas o aplicaciones que los manejan. Anteriormente los programas se codificaban junto con los datos, es decir, se diseñaban para la aplicación concreta que los iba a manejar, lo que desembocaba en una dependencia de los programas respecto a los datos, ya que la estructura de los ficheros va incluida dentro del programa, y cualquier cambio en la estructura del fichero provocaba modificar y
recompilar programas. Además, cada aplicación utiliza ficheros que pueden ser comunes a otras de la misma organización, por lo que se produce una REDUNDANCIA de la información, que provoca mayor ocupación de memoria, laboriosos programas de actualización (unificar datos recogidos por las aplicaciones de los diferentes departamentos), e inconsistencia de datos (no son correctos) si los datos no fueron bien actualizados en todos los programas. Con las bases de datos, se busca
independizar los datos y las aplicaciones, es decir, mantenerlos en espacios diferentes. Los datos residen en memoria y los programas mediante un sistema gestor de bases de datos, manipulan la información. El sistema gestor de bases de datos recibe la petición por parte del programa para manipular los datos y es el encargado de recuperar la información de la base de datos y devolvérsela al programa que la solicitó. Cada programa requerirá de una cierta información de la base de datos, y
podrá haber otros que utilicen los mismos datos, pero realmente residirán en el mismo espacio de almacenamiento y los programas no duplicarán esos datos, si no que trabajarán directamente sobre ellos concurrentemente. Aunque la estructura de la base de datos cambiara, si los datos modificados no afectan a un programa específico, éste no tendrá por qué ser alterado. Mediante estas técnicas de base de datos se pretende conseguir a través del Sistema Gestor de Bases de Datos(SGBD):

* INDEPENDENCIA de los Datos: Cambios en la estructura de la Base de Datos no modifican las aplicaciones. 
* INTEGRIDAD de los Datos: Los datos han de ser siempre correctos. Se establecen una serie de restricciones (reglas de validación) sobre los datos.
* SEGURIDAD de los Datos: Control de acceso a los datos para evitar manipulaciones de estos no deseadas. 

# Definición 

Es una colección de datos referentes a una organización estructurada según un modelo de datos de forma que refleja las relaciones y restricciones existentes entre los objetos del mundo real, y consigue independencia, integridad y seguridad de los datos. 

Lo que debemos tener claro es la diferencia entre Base de Datos y SGBD. La base de datos es el almacenamiento donde residen los datos. El SGBD es el encargado de manipular la información contenida en ese almacenamiento mediante operaciones de lectura/escritura sobre la misma. Además las bases de datos no sólo contendrán las tablas (ficheros) de datos, sino que también almacenará formularios (interfaces para edición de datos), consultas sobre los datos, e informes. El SGBD se encargará de manipular esos datos, controlar la integridad y seguridad de los datos, reconstruir y reestructurar la base de datos cuando sea necesario. 
