## Install and manipulate default values
```sh
helm create app

# --dry-run simulate an install.
helm install --dry-run --set image.tag=1.24.0 -n dev app ./app

# --set set values on the command line
helm install --set image.tag=1.24.0 -n dev app ./app
```

## Upgrade & Rollback
```sh
# Get Image name:tag running inside the pod
kubectl get pods -n dev -o wide
kubectl describe pods -n dev POD_NAME | grep -i image

# Upgrade a release
# --atomic, --cleanup-on-fail, --force
helm upgrade --set image.tag=1.24.0 -n dev app ./app
helm upgrade --set image.tag=1.24.0 --timeout=1m --atomic --cleanup-on-fail -n dev app ./app

# Fetch release history
helm history -n dev app

# Roll back a release to a previous revision
helm rollback -n dev app 1

# uninstall a release
helm uninstall -n dev app
```
