# Aber

## Virtualizacion

Hypervisors. Automation does not come along, but with Ansible / Puppet / Cheff


- VMWare
- Hyper V
- KVM

## Docker

``` bash
docker images

docker history <image>
```

## Kubernetes

Masters
- Control plane(Decitions, scheduler decitions)
    1. API server (Frontend of Control plane)
    2. etcd (key-value db. Stores all cluster config and state)
    3. Scheduler (schedules workloads on nodes)
    4. Cloud Controller Manager (Integration with clouds. Manages networking and Load Balancing)
    5. Kube Controller Manager (Manage controllers on the cluster)
- Watching all, and checking the state

Nodes (Resources of the cluster)
- Runtime environment
    1. Kubelet (Aggent for Kubernetes. Communicate to control plane)
    2. Kube Proxy (Manages Networking in and outta the node)
    3. Container runtime (Allow container management)

Everything in Kubernetes is an object. And every object has state

### Container commands

```bash
docker image tag <image> gcr.io/<PROJECT-ID>/<IMAGE-NAME>:<VERSION>
```

### GKE

#### Node pools

The nodes are part of node pools
