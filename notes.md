# Notes

### [How to use local docker images with Kubernetes?](https://stackoverflow.com/questions/42564058/how-to-use-local-docker-images-with-minikube) - See the solution by Farhad Farahi


### What's the difference between ClusterIP, NodePort and LoadBalancer service types in Kubernetes?

* ClusterIP: Exposes the service on a cluster-internal IP. Choosing this value makes the service only reachable from within the cluster. This is the default ServiceType
* NodePort: Exposes the service on each Node’s IP at a static port (the NodePort). A ClusterIP service, to which the NodePort service will route, is automatically created. You’ll be able to contact the NodePort service, from outside the cluster, by requesting <NodeIP>:<NodePort>.
* LoadBalancer: Exposes the service externally using a cloud provider’s load balancer. NodePort and ClusterIP services, to which the external load balancer will route, are automatically created.

## Resources

* https://kubernetes.io/docs/reference/kubectl/cheatsheet/
* https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/ (ConfigMaps are pods to store configurations)
* helm can be used to install existing charts. Example: https://github.com/adfinis-sygroup/mariadb-galera-chart

## helm

* Docs: https://helm.sh/docs/  [Read templates]
