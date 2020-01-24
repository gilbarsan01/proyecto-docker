Author:Gilberto Barraza gilbarsan@gmail.com

Para iniciar el docker-compose es necesario aplicar la siguiente sentencia:
$ docker-compose up -d
WARNING: The Docker Engine you're using is running in swarm mode.

Compose does not use swarm mode to deploy services to multiple nodes in a swarm. All containers will be scheduled on the current node.

To deploy your application across the swarm, use `docker stack deploy`.

Creating web_nginx_www_1 ... done


validar docker-compose activo:

$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                NAMES
4204f8ac25a7        nginx               "nginx -g 'daemon of…"   2 minutes ago       Up 2 minutes        0.0.0.0:80->80/tcp   web_nginx_www_1


Verificar el servicio de localhost:
$ curl  localhost


Para detener el contenedor:
$ docker-compose  down
Stopping web_nginx_www_1 ... done
Removing web_nginx_www_1 ... done


