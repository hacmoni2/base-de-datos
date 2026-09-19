# Git y GitHub

Git es un sistema de control de versiones distribuido utilizado para registrar y administrar los cambios realizados en un proyecto. Su función principal es mantener un historial de las modificaciones de los archivos, permitiendo consultar versiones anteriores, recuperar cambios y trabajar con diferentes versiones de un proyecto sin perder información. Git fue creado por Linus Torvalds en 2005 y actualmente es una de las herramientas más utilizadas para el desarrollo de software (Git, 2026).

Una característica importante de Git es que funciona de manera distribuida. Esto significa que cada repositorio local contiene una copia del historial del proyecto, por lo que muchas operaciones pueden realizarse sin conexión a Internet. Los cambios pueden registrarse mediante *commits*, que representan puntos específicos en el historial del proyecto. Por ejemplo, después de modificar algunos archivos, pueden utilizarse comandos como `git add` y `git commit` para preparar y registrar los cambios.

GitHub, por otro lado, es una plataforma que permite alojar repositorios de Git en Internet y proporciona herramientas adicionales para colaborar en proyectos. Mientras que Git es el sistema de control de versiones, GitHub es un servicio que utiliza Git como una de sus principales tecnologías. GitHub permite almacenar repositorios de manera remota, compartir proyectos, administrar colaboradores, revisar cambios mediante *pull requests* y utilizar herramientas relacionadas con el desarrollo de software (GitHub, 2026).

Por lo tanto, Git y GitHub no son exactamente lo mismo. Git puede utilizarse completamente de manera local, mientras que GitHub funciona como una plataforma remota para almacenar y colaborar con repositorios. Una computadora puede tener Git instalado y trabajar con repositorios sin utilizar GitHub. Sin embargo, GitHub facilita el intercambio del proyecto entre diferentes equipos y personas.

Para crear un repositorio existen diferentes alternativas. En GitHub puede crearse uno desde la página de la plataforma seleccionando la opción para crear un nuevo repositorio. Se establece un nombre, se determina si será público o privado y pueden agregarse archivos iniciales como un archivo `README`. Posteriormente, el repositorio puede descargarse al equipo mediante `git clone`, creando una copia local que mantiene la conexión con el repositorio remoto.

También es posible crear primero un repositorio local utilizando `git init`. Este comando convierte una carpeta existente en un repositorio de Git. Después pueden agregarse archivos con `git add`, registrar los cambios con `git commit` y establecer un repositorio remoto mediante `git remote add origin`. Finalmente, los cambios pueden enviarse a GitHub mediante `git push`.

Las ramas, conocidas como *branches*, permiten trabajar en diferentes líneas de desarrollo dentro de un mismo repositorio. Una rama puede utilizarse para desarrollar una nueva característica, corregir un error o realizar modificaciones sin afectar directamente la versión principal del proyecto. Generalmente, la rama principal se denomina `main`.

Para crear una rama puede utilizarse el comando:

```bash
git branch nombre-de-la-rama
```

Después, para cambiar a ella se puede utilizar:

```bash
git switch nombre-de-la-rama
```

También es posible crear y cambiar a una rama en una sola instrucción:

```bash
git switch -c nombre-de-la-rama
```

Una vez realizados los cambios dentro de la nueva rama, pueden registrarse mediante un *commit* y posteriormente enviarse al repositorio remoto con `git push`. Esto permite que otros integrantes del proyecto puedan consultar la rama y trabajar sobre ella. Cuando el trabajo está terminado, GitHub permite realizar una *pull request*, mediante la cual los cambios pueden revisarse antes de incorporarlos a la rama principal.

El uso de ramas resulta especialmente importante en proyectos colaborativos porque evita que varios integrantes modifiquen directamente la versión principal al mismo tiempo. Cada integrante puede desarrollar una parte específica del proyecto y posteriormente integrar los cambios. De esta manera, Git proporciona el control del historial y las herramientas para administrar versiones, mientras que GitHub facilita el almacenamiento remoto, la colaboración y la revisión del código.

En conclusión, Git y GitHub cumplen funciones relacionadas pero diferentes. Git proporciona el sistema de control de versiones y permite administrar los cambios de un proyecto, mientras que GitHub ofrece una plataforma para alojar repositorios y facilitar el trabajo colaborativo. El uso de repositorios y ramas permite organizar mejor los proyectos, conservar un historial de modificaciones y reducir los problemas que pueden surgir cuando varias personas trabajan sobre los mismos archivos.

## Referencias

Git. (2026). *Git documentation*. https://git-scm.com/docs

GitHub. (2026). *GitHub documentation*. https://docs.github.com/
