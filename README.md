# ¡Instalación de Docker!

Docker es una plataforma que permite que los desarrolladores puedan crear, probar e implementar aplicaciones rápidamente porque facilita el  empaquetado de diferentes aplicaciones en  **Contenedores**, los cuales incluyen todo lo necesario para que el software se ejecute: Bibliotecas, código y tiempo de ejecución. Docker facilita la implementación y escalabilidad de aplicaciones en cualquier entorno.

## Installation
La página que contiene la documentación oficial de Docker para los diferentes sistemas operativos es : [Get Docker](https://docs.docker.com/get-docker/)

Esta documentación está basada en la instalación de un sistema operativo de **Ubuntu 20.04 LTS**.

Para Desinstalar las versiones anteriores que puedan estar instaladas en nuestro Ubuntu:

```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```

## Instalar usando el repositorio
Antes de instalar Docker Engine por primera vez en una nueva máquina, debe configurar el repositorio de Docker.

## Configuración del repositorio

```docker
$ sudo apt-get update

$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

```

## Agregar la llave oficial de Docker GPG key:
```
 curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

## Instalación de Docker. 
[Docker](https://docs.docker.com/get-docker/)

Actualizar  el índice del paquete apt:

```
$ sudo apt-get update
```
Instalar la última versión de Docker Engine y containerd:

```
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

###### Verificar la instalación:Verificar la instalación:
Para verificar que Docker quedó correctamente instalalado, se puede instalar una imagen de prueba:

```
$ sudo docker run hello-world
```
![](https://github.com/dianaeleira/docker-fedesoft/blob/main/assets/img/hello-world.png)

