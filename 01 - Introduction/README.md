## How to Install
```sh
open https://github.com/helm/helm/releases
wget https://get.helm.sh/helm-v3.13.3-linux-amd64.tar.gz
tar xvf helm-v3.13.3-linux-amd64.tar.gz
sudo mv ./helm /usr/local/bin/
helm version
# version.BuildInfo{Version:"v3.13.3", ...
```

## Add repo
```sh
helm repo list
# Error
helm repo add bitnami https://charts.bitnami.com/bitnami
helm search repo bitnami
helm install my-release bitnami/<chart>
```

## OPTIONAL: auto-completion
``` 
source <(helm completion bash)
```
