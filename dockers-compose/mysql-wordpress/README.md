Author: gilbarsan@gmail.com

-Parametros de configuracion del fichero docker-compose.yaml:
Modificar el docker-compose en la sección de volumen y asignar el path local de su equipo:
~/Dropbox/volumenes-dockers-compose/mysql-wordpress/mysql-data  
por :
~/mysql-data

Para levantar los contenedores es necesario introducir la siguiente sentencia:
$ docker-compose up -d

Para validar el contenido de los contenedores es necesario ingresar la sentencia:
$ docker ps

Una vez iniciado los contenedores es necesario  verificar y accediendo a la URL:8080. 
Ejemplo:  localhost:8080    -> para verificar el Wordpress con mysql configurado.


-Para detener los contenedores :
 $ docker-compose down 

