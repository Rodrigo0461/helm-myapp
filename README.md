# Ejemplo deploy usando Helm

### Pre-requisitos 📋

* Helm V3
* Minikube 

Instalar Minikube en MacOS

```
brew install minikube
```

Instalar Helm en MacOS

```
brew install helm
```

# Helm Create

Nota: Archivos yaml ya fueron generados con helm create, por ende se debe omitir dicho paso.

```
# helm create app-test
```

Helm Create crea la siguente estructura de archivos

```
tree .
.
├── Chart.yaml
├── charts
├── templates
│   ├── NOTES.txt
│   ├── _helpers.tpl
│   ├── deployment.yaml
│   ├── ingress.yaml
│   ├── service.yaml
│   ├── serviceaccount.yaml
│   └── tests
│       └── test-connection.yaml
└── values.yaml
```
# ¿Cómo Despliego? ... Helm Install
```
helm install app-test -f values.yaml deploy --atomic --wait
```
Output

```
NAME: app-test
LAST DEPLOYED: Fri Sep  4 03:03:27 2020
NAMESPACE: test
STATUS: deployed
REVISION: 1
NOTES:
1. Get the application URL by running these commands:
  export NODE_PORT=$(kubectl get --namespace test -o jsonpath="{.spec.ports[0].nodePort}" services rpapp2-helm2-myapp)
  export NODE_IP=$(kubectl get nodes --namespace test -o jsonpath="{.items[0].status.addresses[0].address}")
  echo http://$NODE_IP:$NODE_PORT
```
