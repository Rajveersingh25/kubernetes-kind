# kubernetes-kind
kubernetes-kind

#### Create K8s cluster via Kind command -
kind create cluster --name kuber-ss --config config.yml

#### Get cluster info -
kubectl cluster-info --context kind-kuber-ss

#### Get pods/services/deployments ( resources )
kubectl get nodes/pods/services/deployments
kubectl get pods -n <namespace name>

#### Get Namespaces
kubectl get ns/namespace

#### Create Kubernetes Namaspace
kubect create ns nginx

#### Create Nginx pods
kubectl run nginx --image=nginx:1.28

#### Delete pod/services/deployments
kubectl delete pod <pod-name>

#### Create pod in custom namespace
kubectl run nginx --image=nginx:1.128 -n nginx

#### Delete pods/services/deployment from different namespace
kubectl delete pod nginx -n nginx

#### Describe pod using below commans -
