
REFERNCIA PROYECTO:
https://docs.docker.com/ee/ucp/interlock/usage/tls/


Instrucciones:


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
