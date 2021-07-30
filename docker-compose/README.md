# Archivo docker-compose

Es un archivo texto que contiene un conjunto de comandos o instrucciones. Estos comandos se ejecutan sucesivamente para realizar acciones en la imagen base para crear una nueva imagen de la ventana acoplable.

Para comprender el proceso se procede a crear una carpeta para el proyecto:

```
$ mkdir proxy
$ cd proxy
```
Una vez creado el directorio *proxy* se ingresa a él y se edita el archivo **docker-compose.yml** 
```
$ nano docker-compose.yml
```

Y se adicionan las siguientes líneas:
```
version: '3'
services:
    web:
        image: dockercloud/hello-world
    lb:
        image: dockercloud/haproxy
        links:
            - web
        volumes:
            - /var/run/docker.sock:/var/run/docker.sock
        ports:
            - 80:80
```

Después de guardar el archivo, se procede a crear la imagen:
```
$ docker compose up -d
```
![](https://github.com/dianaeleira/docker-fedesoft/blob/main/assets/img/docker_compose1.png)

##  Visualización de los logs del contenedor
```
$ docker logs <container_id> -f
```
##Establecer la cantidad de contenedores

Con Docker Compose se pueden establecer la cantidad de contenedores que se ejecutarán para un servicio.
```
$ docker-compose up --scale web=5
```
Lo cual permite generar aplicaciones escalables, lo que aumenta su flexibilidad en propiedades tan importantes como consumo de memoria, de espacio en disco. Eso potencia la disponibilidad de un servicio o aplicación.