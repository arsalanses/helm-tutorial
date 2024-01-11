## How to create chart
```sh
# create a new chart with the given name
helm create hello-world

# will lint and verify syntax
helm lint ./hello-world

# locally render templates, [-s only show manifests rendered from the given templates]
helm template ./hello-world
```

## Install chart on cluster
```sh
# create new namespace to keep things clean
kubectl create namespace dev

# Will apply manifests on k8s cluster
# -f specify values in a YAML file
helm install -f hello-world/values.yaml -n dev hello-world ./hello-world

# Lists all of the releases for a specified namespace
helm ls -n dev

# allows using resource name, to select a matching pod to port forward to.
kubectl --namespace dev port-forward $POD_NAME 8080:$CONTAINER_PORT
```
