# unigui-docker
Despliegue de aplicaciones Unigui mediante docker

### Imagen docker que utilizaremos
radstudio/paserver:latest
`docker run -it -e PA_SERVER_PASSWORD=1532 --name paserver -p 64211:64211 -p 8082:8082 -p 8077:8077 -v /home/raulchiclano/unigui-docker/opt:/opt radstudio/paserver:latest`

### Ajuste en el servidor
Descomprimir en ~/unigui-docker/opt
unigui_runtime.zip

Ver [documentación oficial](http://www.unigui.com/doc/online_help/compling--running-a-unigui-app.htm) para obtener los archivos.

### Ajustes previos dentro del contendor
##### Instalamos librerias necesarias:
`sudo apt-get install zlib1g-dev`
##### Exportamos el PATH
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/lib/x86_64-linux-gnu

### Ajuste desde DELPHI:
1. Tools > Options > SDK Manager > Linux 64-bit > Update Local File Cache

2. Configurar en el servermodule el path a los archivos del runtime
```
UniRoot:    /opt/
ExtRoot:    /opt/
```
### Conexión desde Delphi
