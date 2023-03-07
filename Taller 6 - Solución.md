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

![1678224928378](image/Taller6-Solución/1678224928378.png)
![1678224940582](image/Taller6-Solución/1678224940582.png)
![1678225807531](image/Taller6-Solución/1678225807531.png)
![1678225836077](image/Taller6-Solución/1678225836077.png)
![1678225871113](image/Taller6-Solución/1678225871113.png)
![1678225888677](image/Taller6-Solución/1678225888677.png)
![1678226230445](image/Taller6-Solución/1678226230445.png)
