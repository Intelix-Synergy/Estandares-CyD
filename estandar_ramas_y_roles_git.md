![Intelix Logo](http://cs.intelix.biz/logo/pic.png)

# Perfiles, ramas y versionamiento para proyectos

<center>v-1.0.1</center>
---

Este documento describe el estandar para el marco de trabajo de nuestro control de versiones.

*  Roles

Esta matríz de rolers ha sido realizada con base a la documentación oficial de git, implementando el esquema de trabajo git flow y adaptada a Intelix

Se describen los siguientes roles


    admin / owner -> rol para el líder de aplicaciones del área y administradores de repositorio
    mantainer -> rol para el líder técnico del proyecto
    developer -> rol para los desarrolladores del proyecto
    guest / reporter -> rol para el líder de proyecto con la finalidad que permita la creación de defectos

![Perfiles](/home/malvarado/Escritorio/Cuadro_perfiles.png)

<br/>
___

*  Ramas

Se manejarán 3 ramas principales:


**Master (protegida)** : será la rama principal la cual contendrá las etiquetas con las versiónes estables y desplegadas en producción.
**Releases (protegida) **: será la rama que contendrá las etiquetas con las versiones que se encuentran en fase de certificación, copia de master con las integraciones o mezclas de código provenientes de desarrollo.
**Develop (protegida) **: será la rama que contrendrá la línea de desarrollo actual del proyecto.

El resto de ramas son catalogadas como temporales y permitidas : **features, hotfix, support, etc**

Las ramas temporales serán limpiadas y eliminadas bajo jornadas de mantenimiento sin previo aviso y no serán consideradas ramas finales a efectos de despliegues a ambientes de calidad o producción.

<br/>
___ 

*  Versionamiento

 
El formato de versión para las etiquetas a implementar será en basado en 3 dígitos, de la siquiente forma:
**Producción** : v-X.Y.Z
**Calidad** : v-X.Y.Z-snapshot
**Desarrollo** : v-X.Y.Z-unstable


    El primero (X) se le conoce como versión mayor y nos indica la versión principal del software. Ejemplo: 1.0.0, 3.0.0
    El segundo (Y) se le conoce como versión menor y nos indica nuevas funcionalidades. Ejemplo: 1.2.0, 3.3.0
    El tercero (Z) se le conoce como revisión y nos indica que se hizo una revisión del código por algun fallo. Ejemplo: 1.2.2, 3.3.4

 

Procedimiento para el cambio de cada dígito de versión.

    Versión mayor o X, cuando agreguemos nuevas funcionalidades importantes, puede ser como un nuevo modulo o característica clave para la funcionalidad.
    Versión menor o Y, en Intelix este dígito no es un incremental 1 + 1, en su lugar será un indicativo de las cantidades de nuevas funcionalidades incorporadas en cada versión.
    Revisión o Z, en Intelix usado para llevar el control de la cantidad de defectos que se corrigieron en la versión.

<br/>
___ 

*  Estructura

 

La estructura de los proyectos, grupos, etc dentro de nuestro esquema de control de versiones tendrá 2 grandes ramas según la plataforma que hoy manejamos y será de la siguiente manera:

 

**Aplicaciones RPG**

Se crean grupos por silos : Compras, Ventas, Logística, etc.

Se agisnan los usuarios correspondiente a cada silo.

 
**Aplicaciones NO RPG**

Esta estructura agrupa el resto de nuestras aplicaciones independientemente del lenguaje en el que se desarrolle como sigue:
Se crean grupos por servicio, proyecto macro o línea de desarrollo: BI, ABX, RA, IA, etc.
Los nombres de los grupos serán a nombre completo : Realidad Aumentada, Inteligencia Artificial, etc
Se asignan los integrantes correspondientes a cada servicio.

 
**Consideraciones adicionales**
 
Cada proyecto deberá contener el archivo de documentación técnica (README.md) debidamente lleno para poder ser considerado como una aplicación a desplegar, el formato o plantilla a llenar de este documento será cargado por Configuración y Despliegue en cada proyecto que corresponda.
 
De acuerdo con los esquemas de seguridad establecidos, las conexiones desde y hacia el repositorio de control de versiones serán realizadas bajo https.
 
Aún cuando no se limita el uso de git flow como plugin de administración y manejo de ramas dentro de los proyectos, el mismo no forma parte del estandar por el momento.