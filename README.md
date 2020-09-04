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

# ¿Cómo Despliego?

Nota: Archivos yaml ya fueron generados con helm create, por ende se omite dicho paso

```
helm install app-test -f values.yaml deploy --atomic --wait
```
Output

```
NAME: rpapp
LAST DEPLOYED: Fri Sep  4 02:56:12 2020
NAMESPACE: test
STATUS: deployed
REVISION: 1
NOTES:
1. Get the application URL by running these commands:
  export POD_NAME=$(kubectl get pods --namespace test -l "app.kubernetes.io/name=helm2-myapp,app.kubernetes.io/instance=rpapp" -o jsonpath="{.items[0].metadata.name}")
  echo "Visit http://127.0.0.1:8080 to use your application"
  kubectl --namespace test port-forward $POD_NAME 8080:80
```
