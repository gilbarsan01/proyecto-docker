
REFERNCIA PROYECTO:
https://docs.docker.com/ee/ucp/interlock/usage/tls/


Instrucciones:


-inicializar proyecto SWARM
gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$ docker swarm init
Swarm initialized: current node (kmosjnr7139offm21pq8uk6pk) is now a manager.

To add a worker to this swarm, run the following command:

    docker swarm join --token SWMTKN-1-2zle55s31599e6dvqeyyi9y19jkgwhwh24n2vrp9l1ibrwau5y-6x9rtvo8k8zsm9g2ik8zjir15 192.168.100.13:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.

gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$ 

-Levantar contenedor:
gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$ docker stack deploy --compose-file docker-compose.yml demo
Updating service demo_demo (id: bkia01rdxo8g5fw7s5skr36j1)
gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$ 


-Verificar contenedor docker:
gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$ docker ps
CONTAINER ID        IMAGE                         COMMAND              CREATED             STATUS              PORTS               NAMES
9da584588a4f        ehazlett/docker-demo:latest   "/bin/docker-demo"   53 seconds ago      Up 43 seconds       8080/tcp            demo_demo.1.r31274d3idom39qhkk187rdra


-Obtener direccion IP de contenedor:
gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$ docker exec -it 9da584588a4f ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
622: eth0@if623: <BROADCAST,MULTICAST,UP,LOWER_UP,M-DOWN> mtu 1450 qdisc noqueue state UP 
    link/ether 02:42:0a:00:00:0a brd ff:ff:ff:ff:ff:ff
    inet 10.0.0.10/24 brd 10.0.0.255 scope global eth0
       valid_lft forever preferred_lft forever
624: eth1@if625: <BROADCAST,MULTICAST,UP,LOWER_UP,M-DOWN> mtu 1500 qdisc noqueue state UP 
    link/ether 02:42:ac:14:00:03 brd ff:ff:ff:ff:ff:ff
    inet 172.20.0.3/16 brd 172.20.255.255 scope global eth1
       valid_lft forever preferred_lft forever
gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$ 



Verificar el contenedor:
https://172.20.0.3:8080/



-Detener servicio:
gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$ docker stack rm demo
Removing service demo_demo
Removing secret demo_app.example.org.cert
Removing secret demo_app.example.org.key
Removing network demo_demo-network
gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$


-Se valida   que ya no este corriendo:
gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
gilbarsan@HP-Pavilion-17-Notebook:~/repos/github/proyecto-docker/dockers-compose/tls_web$ 

