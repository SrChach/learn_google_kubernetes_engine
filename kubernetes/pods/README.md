# Pods

Aqui probaremos los pods de una manera declarativa

## Single container

El archivo `nginx.yaml` tiene un Pod con un único container del WebServer nginx, corriendo y exponiéndolo en un puerto dado.

Podemos acceder a él desde el preview web de GCP haciendo un tunel, como sigue:

``` bash
kubectl port-forward nginx 8080:80
```

## Multi container

El archivo `multicontainer.yaml` contiene un Pod con dos containers, que comparten un almacenamiento temporal (Volume emptyDir).

- Un server ftp
- Un webServer nginx para responder solicitudes web

Al "compartir" un directorio (un puntero hacia el almacenamiento compartido), si modificamos el directorio compartido, se modificará en ambos. Haremos pruebas con esto, entrando al container, escribiendo algo en el directorio expuesto y luego haciendo una petición a la red compartida dentro del pod

``` bash
kubectl exec -it multicontainer -c ftp-container -- /bin/bash

echo "Bibo en el almacenamiento compartido" >> /pod-data/index.html
curl http://localhost/
```

