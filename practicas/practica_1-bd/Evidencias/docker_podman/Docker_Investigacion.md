# El sistema gestor en un contenedor: Docker

## Parte A. Investigación

Un contenedor es un paquete de software ligero, autónomo y ejecutable que incluye todo lo necesario para que una aplicación funcione. Funciona como un proceso aislado en el sistema operativo anfitrión. Una maquina virtual en comparación requiere arrancar un sistema.

Las maquinas virtuales son mas pesadas porque incluyen su propio sistema operativo invitado. Los contenedores comparten el kernel del sistema operativo de la máquina anfitriona y son sumamente ligeros.

Las maquinas virtuales ofrecen aislamiento a nivel de hardware mediante un hipervisor. Los contenedores ofrecen aislamiento a nivel de procesos y sistemas de archivos, lo que garantiza que la aplicación esté aislada del anfitrión y de otros contenedores sin la perdida de rendimiento por virtualizar el hardware.

- *Imagen:* Para montar un contenedor necesitamos una imagen que es una plantilla de solo lectura compuesta por capas que contiene las instrucciones para crearlo. 
- *Contenedor:* Es una instancia ejecutable de la imagen. Mientras que la imagen es estática, el contenedor es el entorno dinámico y en ejecución donde la aplicación funciona.
- *Volumen:* Es el mecanismo para persistir datos generados y utilizados por un contenedor. Permite que la información sobreviva más allá del ciclo de vida del contenedor, almacenándose directamente en el sistema de archivos del anfitrión de manera independiente. Si no se define, todos los datos se eliminaran generados durante la ejecución del contenedor se eliminaran junto con este el momento en que se detenga.
- *Puerto publicado:* Dado que los contemedores se ejecutan en una red interna se debe públicar un puerto físico, el cual se va a conectar al puerto interno del contenedor para poder acceder a él.

## Fuentes

Docker. (n.d.). Docker documentation. Recuperado el 18 de septiembre de 2026, de https://docs.docker.com/