Genera una nueva imagen con el tag ubuntu:1.2 
docker build -t ubuntu:1.2 .

Ejecutar contenedor con la imagen generada:
docker run ubuntu:1.2 ls /tmp/
