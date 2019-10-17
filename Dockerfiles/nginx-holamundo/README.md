Generar imagen del ~/Dockerfile:
$ docker build -t mynginx:1.1 .

Ejecutar Docker (--name nombre_contenedor -p PuertoAnfritrion:PuertoContenedor -d ImagenGenerada):
$ docker run --name mynginx2 -p 8080:80 -d mynginx:1.1

Validar contenedor: 
$ curl localhost:8080
Hola mundo desde contenedor - Web NGINX
$ 
