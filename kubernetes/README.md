# Kubernetes Engine

## Nodes

Para listar los Pods dentro de un Nodo, con la info de un nodo, corremos el siguiente comando

``` bash
# -o is for output format
kubectl get pods -o=<OUTPUT_CONFIGURATION>
kubectl get pods -o=custom-columns=NODE:.spec.nodeName,PODNAME:metadata.name

# Corromper nodo
kubectl taint nodes <NODES> key=<TAINT_OPTIONS>
kubectl taint nodes gke-kluster-default-pool-8850897b-9905 key=value:NoSchedule

# Des-corromper nodo xd
kubectl taint nodes gke-kluster-default-pool-8850897b-9905 key:NoSchedule-
```
