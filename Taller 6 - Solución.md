# Taller 6

### Docker

##### Analítica Computacional para la Toma de Decisiones

---

|     Nombres      |      Apellidos       |     Login     |  Codigo   |
| :--------------: | :------------------: | :-----------: | :-------: |
|     Santiago     | Gonzalez Montealegre | s.gonzalez35  | 202012274 |
| Juliana Carolina |  Cardenas Barragan   | jc.cardenasb1 | 202011683 |

---

---

## 1. Instale Docker y lance su primer contenedor de prueba

---

Nombre grupo e instancia: `Analistas6`
IP: 34.239.253.176
IP2: 54.87.237.118

![1678223620878](image/Taller6-Solución/1678223620878.png)
![1678223636672](image/Taller6-Solución/1678223636672.png)
![1678223706486](image/Taller6-Solución/1678223706486.png)
![1678223754898](image/Taller6-Solución/1678223754898.png)
![1678223874828](image/Taller6-Solución/1678223874828.png)
![1678224092191](image/Taller6-Solución/1678224092191.png)
![1678224102166](image/Taller6-Solución/1678224102166.png)
![1678224232872](image/Taller6-Solución/1678224232872.png)
![1678224282950](image/Taller6-Solución/1678224282950.png)

11. Copie la salida en pantalla en su reporte

```shell
ubuntu@ip-172-31-56-22:~$ sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete
Digest: sha256:6e8b6f026e0b9c419ea0fd02d3905dd0952ad1feea67543f525c73a0a790fefb
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

---

---

## 2. Lance una aplicación sencilla en Python en un Docker

---

2. Abra el archivo Dockerfile y describa su contenido en su reporte. Para esto tenga presente que

- FROM determina la imagen base que se usa como sistema operativo y aplicaciones iniciales.
- RUN ejecuta comandos al interior del contenedor.
- COPY copia archivos del sistema hospedador (la máquina virtual) al contenedor.
- ENV permite definir variables de entorno.
- EXPOSE abre un puerto del contenedor.
- CMD es el comando que se ejecuta al lanzar el contenedor.

`syntax=docker/dockerfile:1`

La primera línea define la versión de la sintaxis del Dockerfile. En este caso, se está usando la versión 1 de la sintaxis de Docker.

`FROM ubuntu:22.04`

La segunda línea indica la imagen base que se va a utilizar para construir la imagen de Docker. En este caso, se está utilizando la imagen de Ubuntu 22.04.

`install app dependencies`
`RUN apt-get update && apt-get install -y python3 python3-pip`

La tercera línea ejecuta un comando dentro de la imagen para instalar las dependencias necesarias para la aplicación. En este caso, se están actualizando los paquetes de Ubuntu con `apt-get update`, y luego con `apt-get install` se están instalando `python3` y `python3-pip`.

`RUN pip install flask==2.1.*`

La cuarta línea instala la librería `Flask` de Python usando el comando `pip install`. En este caso, se está instalando la versión `2.1.*` de Flask al interior del
contenedor.

`install app`
`COPY hello.py /`

La quinta línea copia el archivo `hello.py` desde la ruta actual del sistema hospedador en el que se está construyendo el Docker al contenedor.
Esto significa que el archivo `hello.py` estará disponible en la imagen de Docker.

`final configuration`
`ENV FLASK_APP=hello`

La sexta línea establece una variable de entorno llamada `FLASK_APP` con el valor hello. Esto indica a Flask que debe usar el archivo `hello.py` como la aplicación
de Flask principal

`EXPOSE 8000`

La séptima línea expone el puerto `8000` de la imagen. Esto significa que, cuando se ejecute la imagen de Docker, se podrá acceder a la aplicación a través del puerto `8000`.

`CMD flask run --host 0.0.0.0 --port 8000`

La última línea establece el comando que se ejecutará cuando se inicie el contenedor. En este caso, el comando es flask run, lo que iniciará la aplicación Flask. Los argumentos `--host 0.0.0.0` y `--port 8000` indican que la aplicación debe escuchar en todas las direcciones IP (0.0.0.0) y en el puerto 8000.

![1678224928378](image/Taller6-Solución/1678224928378.png)
![1678224940582](image/Taller6-Solución/1678224940582.png)
![1678225807531](image/Taller6-Solución/1678225807531.png)
![1678225836077](image/Taller6-Solución/1678225836077.png)
![1678225871113](image/Taller6-Solución/1678225871113.png)
![1678225888677](image/Taller6-Solución/1678225888677.png)
![1678226230445](image/Taller6-Solución/1678226230445.png)

---

---

## 3. Lanzando otros contenedores

1. Lance un nuevo contenedor y conéctese a la terminal interactiva del mismo usando
bash con el comando

2. Note que en este caso ha quedado conectado a la terminal del contenedor. En la
terminal del contenedor verifique la estructura de archivos con ls. En su reporte
incluya las carpetas disponibles en el directorio raíz.

4. Liste todos los contenedores disponibles con el comando
`sudo docker ps -a`
Incluya un pantallazo con el listado y sus caracter´ısticas en su reporte.

7. Liste todos los archivos en esta carpeta en su reporte

8. Explore el Dockerfile, ¿qué informaci´on encuentra allí? Explique los comandos en
su reporte.

9. Explore el package.json, ¿qué informaci´on encuentra allí? Inclúyala en su reporte.

12. Liste todos los contenedores disponibles con el comando
`sudo docker ps -a`
Incluya un pantallazo con el listado y sus características en su reporte.

13. Abra el puerto 8000 en su instancia y explore en el navegador la aplicación lanzada.
En su reporte explique por qué en este caso se publica en los puertos 8000:8080 y
antes se hacía en 8000:8000.

![1678397641818](image/Taller6-Solución/1678397641818.png)

![1678397719388](image/Taller6-Solución/1678397719388.png)

![1678397733053](image/Taller6-Solución/1678397733053.png)
![1678397884550](image/Taller6-Solución/1678397884550.png)

![1678398086305](image/Taller6-Solución/1678398086305.png)
![1678398135919](image/Taller6-Solución/1678398135919.png)
![1678398737107](image/Taller6-Solución/1678398737107.png)

```
FROM node:current-slim

WORKDIR /usr/src/app
COPY package.json .
RUN npm install

EXPOSE 8080
CMD [ "npm", "start" ]

COPY . .
```

![1678398780028](image/Taller6-Solución/1678398780028.png)

```
{
  "name": "vue-event-bulletin",
  "version": "1.0.0",
  "description": "Demo application for the scotch.io tutorial",
  "main": "server.js",
  "author": "Ryan Chenkie, Jason Lam",
  "license": "MIT",
  "dependencies": {
    "bootstrap": "^3.3.6",
    "ejs": "^2.3.4",
    "express": "^4.13.3",
    "morgan": "^1.6.1",
    "vue": "^1.0.10",
    "vue-resource": "^0.1.17"
  },
  "devDependencies": {
    "body-parser": "^1.14.1",
    "errorhandler": "^1.4.2",
    "method-override": "^2.3.5",
    "morgan": "^1.6.1"
  },
  "scripts": {
    "start": "node server.js"
  }
}
```

## 4. Mas operaciones en Docker

1. Liste las im´agenes locales
`sudo docker image ls`
Incluya el resultado en su reporte.

2. Liste los contenedores locales en ejecuci´on.
`sudo docker container ls`
Incluya el resultado en su reporte.

3. Liste todos los contenedores locales.
`sudo docker container ls -a`
Incluya el resultado en su reporte. Describa las diferencias entre im´agenes, contenedores y contenedores en ejecuci´ons.

4. Intente eliminar la imagen hello-world
`sudo docker image rm hello - world`
Incluya el resultado en su reporte. ¿Por qu´e no es posible eliminar la imagen?

5. Elimine imagen hello-world
`sudo docker image rm --force hello - world`
Incluya el resultado en su reporte. Verifique que la imagen (y el contenedor asociado) se hayan eliminado. Incluya un pantallazo de los comandos y la salida en su
reporte.

6. Traiga la imagen de hello-world del registro
`sudo docker pull hello - world`
Incluya el resultado y su interpretaci´on en su reporte. Verifique que la imagen se
encuentre localmente.

8. Traiga la imagen del servidor web apache (httpd) del registro
`sudo docker pull httpd`
Incluya el resultado y su interpretaci´on en su reporte. Verifique que la imagen se
encuentre localmente

9. Verifique que la imagen se encuentre localmente
`sudo docker images`
Incluya un pantallazo del resultado en su reporte.

10. Usando esta imagen lance un contenedor con nombre docker-apache y acople el
puerto 80 de la m´aquina con el puerto 80 del contenedor
`sudo docker run -d --name docker - apache -p 80:80 -d httpd`
El servidor debe estar corriendo por el puerto 80, luego debe poder accederlo desde
el navegador solamente con la IP. Incluya un pantallazo del resultado en su reporte.

12. Pruebe ahora a detener el contenedor con el comando
`sudo docker container stop docker - apache`
Verifique en su navegador que el servicio se ha detenido. Tome un pantallazo para
su reporte.

13. Reinicie nuevamente contenedor con el comando
`sudo docker container start docker - apache`
Verifique en su navegador que el servicio ha regresado. Tome un pantallazo para su
reporte.

14. Para ver los ´ultimos 10 registros del log de su contenedor ejecute el comando
`sudo docker container logs --tail 10 docker-apache`
Incluya el resultado en su reporte.

19. Env´ıe por Slack e incluya en su reporte el enlace a su repositorio con la imagen.