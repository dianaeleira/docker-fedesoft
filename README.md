
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