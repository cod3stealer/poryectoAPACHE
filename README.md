# proyectoAPACHE

Lo primero es crear la carpeta que contendrá todo lo que se quiera hacer.
Mi carpeta "server" contiene las carpetas "sitio1, sitio2, sitio HTTPS y sitioSSL". 

Por otro lado, también contiene los archivos docker-compose.yml (el cual creo de manera manual 
igual que los demás archivos), info.php, README.md

Dentro del docker-compose.yml declaro el contenedor con su imagen, puerto y volumenes

```
version: "3.3"
services:
 apache-XD:
  container_name: apache-XD
  image: php:7.2-apache
  ports:
    - "80:80"
  volumes:
    - /home/asir2a/Escritorio/SRI/tuto/server:/var/www/html
    - configApache:/etc/apache2
volumes:
  configApache:
```
En ~/server/info.php pongo: 
```
<?php
    phpinfo();
?>
```
Una vez esto está hecho, dentro de sitio1/ creo un archivo llamado index.html en el cual pongo `<h1>hola mundo</h1>`
Ahora lo que hago es ejecutar docker-compose up y en el navegador buscar **localhost:80**
