# Services

El tipo por defecto de los servicios es ClusterIp

``` yaml
# Tipo, y nombre del objeto en Metadata
apiVersion: v1
kind: Service
metadata:
  name: nginx-service

spec:
  # Selectores, para seleccionar que objetos mostrar en el servicio
  selector:
    app: nginx
  # Puertos
  ports:
    - protocol: TCP
      port: 80 # Puerto del cluster
      targetPort: 80 # Puerto expuesto de los contenedores
```