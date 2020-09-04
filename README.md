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
helm install <name> -f values.yaml deploy --atomic --wait
```
