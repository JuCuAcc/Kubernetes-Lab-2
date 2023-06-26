# Kubernetes Commands 

## Some Kubernetes Commands Used in this Lab

1. `kubectl version`: Displays the Kubernetes client and server versions.
2. `kubectl config get-clusters`: Lists the names of all clusters configured in the `kubectl` configuration file.
3. `kubectl config get-contexts`: Lists all the contexts configured in the `kubectl` configuration file.
4. `kubectl get pods`: Lists all the pods running in the current namespace.
5. `kubectl get pods -o wide`: Lists all the pods running in the current namespace with additional details.
6. `kubectl run hello-world --image us.icr.io/$MY_NAMESPACE/hello-world:1 --overrides='{"spec":{"template":{"spec":{"imagePullSecrets":[{"name":"icr"}]}}}}'`: Creates a new deployment named "hello-world" with a specified container image and overrides the pod's specifications.
7. `kubectl describe pod hello-world`: Provides detailed information about a specific pod named "hello-world".
8. `kubectl delete pod hello-world`: Deletes the pod named "hello-world".
9. `kubectl get pods`: Lists all the pods running in the current namespace after the previous delete command.
10. `kubectl create -f hello-world-create.yaml`: Creates Kubernetes resources defined in the YAML file named "hello-world-create.yaml".
11. `kubectl get pods`: Lists all the pods running in the current namespace after the previous delete command.
12. `kubectl delete pod hello-world-557f7d8b65-fmgnp && kubectl get pods`: Deletes a specific pod named "hello-world-557f7d8b65-fmgnp" and then lists all the pods running in the current namespace.
13. `kubectl expose deployment/hello-world`: Creates a service to expose the pods managed by the deployment named "hello-world".
14. `kubectl get services`: Lists all the services running in the current namespace.
15. `kubectl proxy`: Starts a proxy server to access the Kubernetes API locally.
16. `curl -L localhost:8001/api/v1/namespaces/sn-labs-$USERNAME/services/hello-world/proxy`: Sends an HTTP GET request to the specified URL, retrieving information about the service.
17. ```bash
    for i in `seq 10`; do curl -L localhost:8001/api/v1/namespaces/sn-labs-$USERNAME/services/hello-world/proxy; done
    ```: Executes the `curl` command ten times in a loop, sending HTTP GET requests to the specified URL.
18. `kubectl delete deployment/hello-world service/hello-world`: Deletes both the deployment and service named "hello-world".

---
