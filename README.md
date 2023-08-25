# k8s-apps

## 開発環境

k8s on minikube on Docker on Ubunts というわかりにくい環境となっています。

- OS : Ubuntu 22.04.3 LTS on WSL2(Windows 11 Home)
- Docker : v24.0.5
- minikube : v1.31.1
- Kubernetes : v1.27.3
- pip : 22.0.2
- ArgoCD CLI : v2.8.0

## 環境構築

```
pip install -r requirements.txt
pre-commit install
```

## httpbin(Namespace,Deployment,Service,Ingress)

```
kubectl apply -f webservice1/httpbin
sudo ssh -N -i $(minikube ssh-key) -L 80:localhost:80 docker@$(minikube ip)
```
