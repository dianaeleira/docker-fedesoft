# ¡Instalación del servidor Nginx!

Nginx es un servidor web/proxy inverso ligero de alto rendimiento y un proxy para protocolos de correo electrónico. Es software libre y de código abierto, licenciado bajo la Licencia BSD simplificada; también existe una versión comercial distribuida bajo el nombre de Nginx Plus.

## Instalación
La página que contiene la documentación oficial de Nginx  es : [Nginx](https://www.nginx.com/)

El primer paso que se va a realizar en este ejercicio para trabajar con el servidor **Nginx** es crear una carpeta de trabajo, *mi-primer-dockerfile*:

```bash
$ cd mi-primer-dockerfile
```
Se debe editar un archivo llamado Dockerfile:
```
$ nano Dockerfile
```
Y dentro de él debe agregar las siguientes líneas:
```
FROM nginx
COPY static-html-directory /usr/share/nginx/html
```

A continuación se crea un directorio adicional dentro de *mi-primer-dockerfile/* se debe crear la supcarpeta *static-html-directory*. Dentro de esta subcarpeta se debe editar un archivo *index.html*

```
$ mkdir static-html-directory
$ cd static-html-directory
$ nano index.html
```

Dentro del archivo *index.html* se agrega la siguiente línea:
```
hello world
```

## Construcción de la imagen
Después de guardar los cambios y salir, se debe ubicar nuevamente en el directorio padre, es decir *mi-primer-dockerfile/*:

```
$ cd ..
$ ls
```
```
Dockerfile  static-html-directory
```
En seguida, se construye la imagen de arranque con el siguiente línea de comando:
```
$ docker image build -t some-content-nginx .
```
![](https://github.com/dianaeleira/docker-fedesoft/blob/main/assets/img/docker_nginx.png)

Para verificar que la imagen se haya construído correctamente, se lista con el comando:
```
$ docker image ls
```
![](https://github.com/dianaeleira/docker-fedesoft/blob/main/assets/img/docker_nginx_ls.png)

## Arranque del Servidor
Para iniciar el servidor, se toma el contenido de la carpeta *static-html-directory* y se ejecuta la imagen sobre el puerto 8080:
```
$ docker run --name some-nginx -d -p 8080:80 some-content-nginx
```
![](https://github.com/dianaeleira/docker-fedesoft/blob/main/assets/img/docker_nginx_arranque.png)

Y para verificar la correcta ejecución del servidor sobre el puerto 80, se ejecuta la siguiente línea de comando: 
```
curl -k localhost:8080
```
![](https://github.com/dianaeleira/docker-fedesoft/blob/main/assets/img/docker_nginx_helloworld.png)