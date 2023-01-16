# Deployments

Partes de un deployment

``` yaml
# API version. Object type
apiVersion: apps/v1
kind: Deployment

# Metadata. Naming and labeling
metadata:
  name: nginx-deployment
  labels:
    app: nginx

# Specification
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    containers:
      - name: nginx
        image: nginx:1.7.9
        ports:
          - containerPort: 80
```

## Comandos

Nota: el nombre del deployment se ubica en `metadata/name`

``` bash
kubectl describe deployment <DEPLOYMENT-NAME>

# Example
kubectl describe deployment myapp-deployment
```

### Status de cambios

Al ejecutar un cambio, podemos saber el estatus del cambio con el siguiente comando

``` bash
# Ver status de cambio
kubectl rollout status deployments.v1.apps/myapp-deployment

# Ver historial de cambios
kubectl rollout history deployment.v1.apps/myapp-deployment

# Deshacer ultimo cambio
kubectl rollout undo deployment.v1.apps/myapp-deployment
```