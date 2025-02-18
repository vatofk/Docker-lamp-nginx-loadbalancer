

###  Comando para crear una subnet via CLI
###  Util para crear redes independientes por cada servicio o contenedor

```docker network create --driver bridge --subnet=x.x.x.x/24 nombre_subnet```
________________________________________________________________________

###  Agregar esto al final del docker-compose.yaml para poder usar una subnet creada de forma externa (via CLI)
###  Permite usar alguna de las redes creadas manualmente y evitar crearla dentro del docker-compose.yaml
```
networks:
  red_nginx:
    external: true 
```
________________________________________________________________________

###  Lista las networks disponibles

```docker network ls```
________________________________________________________________________

###  Para ver informacion de la network

```docker network inspect nombre_subnet```
________________________________________________________________________

###  Para eliminar una network

```docker network rm nombre_subnet```
________________________________________________________________________

###  Comando para detener todos los contenedores a la vez (CMD WINDOWS) 

```for /f "tokens=*" %i in ('docker ps -q') do docker stop %i```
________________________________________________________________________

###  Comando para detener todos los contenedores a la vez (PowerShell WINDOWS) 
```docker ps -q | ForEach-Object { docker stop $_ }```
________________________________________________________________________

###  Comando para detener todos los contenedores a la vez (Linux o macOS) 

```docker stop $(docker ps -a -q)```
________________________________________________________________________

###  Comando para detener todos los contenedores a la vez (Linux, macOS, Windows WSL)
```docker ps -a -q | xargs docker stop```
________________________________________________________________________