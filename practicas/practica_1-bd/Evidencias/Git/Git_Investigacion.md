# Control de versiones con Git y GitHub

## Parte A. Investigación

Un control de versiones es un sistema que registra los cambios realizados en un archivo o conjunto de archivos a lo largo del tiempo, de modo que se puedan recuperar versiones específicas más adelante.  

Los sistemas de control de versiones locales almacenan los cambios realizados a los archivos en una base de datos siendo capaz de recrear un archivo a como era en cualquier momento, sin embargo esto no sirve para proyecto colaborativos.

Para proyectos colaborativos se usan sistemas de control de versiones centralizados que versionan los archivos en un servidor central, pudiendo descargar los archivos varios clientes en cualquier momento. La falla de este tipo de sistemas es que dependen del servidor central y en caso de que llegue a fallar se puede perder todo el proyecto.

Git es un sistema de control de versiones distribuido, los clientes no solo descargan la última copia de los archivos, sino que se replica completamente el repositorio. De esta manera si un servidor falla, cualquiera de los repositorios de los clientes puede ser copiado al servidor con el fin de restaurarlo. Además, muchos de estos sistemas se encargan de manejar numerosos repositorios remotos con los cuales pueden trabajar, de tal forma que puedes colaborar simultáneamente con diferentes grupos de personas en distintas maneras dentro del mismo proyecto.

GitHub se basa en el software de código abierto, Git.

Git es un sistema de control de versiones que realiza un seguimiento de los cambios en los archivos. Le permite trabajar en su propia copia de un proyecto, registrar un historial de los cambios y combinar su trabajo con los cambios de otras personas de forma segura.

GitHub se basa en Git mediante el hospedaje de los proyectos de Git, denominados repositorios, en la nube, así como la adición de herramientas de planeación y colaboración que facilitan a los equipos trabajar juntos.

El uso de ramas en Git, consiste en crear una copia de la imagen actual de la rama principal y trabajar sobre ésta misma para probar los cambios antes de fusionarla con la rama principal. 

En Git cada commit del proyecto crea un "apuntador" al commit o commits padres y a la imagen del proyecto en ese momento. Debido esto y a que cada rama no es más que un apuntador al ultimo commit, la creación y fusión de ramas es demasiado rápida.

### Definiciones:

- *Repositorio:* Es donde se almacenan y gestionan los archivos de nuestro proyecto.
- *Commit:* Es la confirmación de cada cambio que se realiza en nuestro repositorio.
- *Branch:* Una rama del proyecto es una versión del proyecto que se modifica de forma aislada para no alterar el código principal del proyecto.
- *Merge:* Es la fusión de una rama con otra, pudiendo ser la pincipal.
- *Conflicto de fusión:* Ocurre cuando en dos ramas se realizaron modificaciones distintas del mismo archivo y por lo tanto no se puede decidir de manera automatica que cambio conservar en la fusión.
- *Pull request:* Es la petición para integrar los cambios realizados en una rama a la principal.
- *Archivo .gitignore:* Sirve para indicar a Git que archivos del repositorio no deben ser versionados.
- *Archivo README:* Sirve para explicar el proyecto a cualquier persona que quiera trabajar en éste.

## Fuentes

https://git-scm.com/book/es/v2

https://docs.github.com/es/get-started/start-your-journey/what-is-github