# k8s-apps

## 開発環境

k8s on minikube on Docker on Ubunts というわかりにくい環境となっています。

- OS : Ubuntu 22.04.3 LTS on WSL2(Windows 11 Home)
- Docker : v24.0.6
- minikube : v1.31.1
- Kubernetes : v1.27.4
- pip : 22.0.2

## 環境構築

```
pip install -r requirements.txt
pre-commit install
```

## httpbin,go

```
kubectl apply -f webservice1/httpbin
kubectl apply -f webservice1/go
```

### Nginx(blue,green)

```
kustomize build ./webservice1/nginx/overlays/blue/ | kubectl apply -f -
kustomize build ./webservice1/nginx/overlays/green/ | kubectl apply -f -
```