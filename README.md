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
kubect describe pods nginx -n ngix

#### Deploy via manifest -
kubectl apply -f nginx.yml/pods/yml -n nginx
kubectl apply -f deployment.yml -n nginx

#### Enter inside the pod
kubectl exec -it pod/nginx-pod -n nginx -- bash

#### Get Deployments.pods -
kubectl get deployments -n nginx
kubectl get pods -n nginx

#### Scale the pods -
kubectl scale deployment/nginx-deployment -n nginx --replicas=5

#### TO get more information about the pods -
kubectl get pods -n nginx -o wide

#### To rollout or update pods -
kubectl set image deployment/nginx-deployment -n nginx nginx=nginx:1.27.3

#### Get all the resources in specific namespaces 
kubectl get all -n nginx

#### Forward port with external network -
kubectl port-forward service/nginx-service -n nginx 8080:80 --address=0.0.0.0
sudo -E kubectl port-forward service/nginx-service -n nginx 80:80 --address=0.0.0.0


#### Get all resources in the namespace -
kubectl get all -n nginx

#### Get secrets with base64 encoded -
echo "root@1223@#" | base64

#### Check current kubernetes user -
kubectl auth whoami

#### Create helm chart -
helm create apache-helm

#### To pacakge helm repository -
helm package apache-helm/

#### Create new environment with helm package -
helm install dev-apache apache-helm
helm install dev-apache apache-helm -n dev-apache --create-namespace

#### Unisntall any helm environment -
helm uninstall dev-apache

#### Upgrade new version -
helm package apache-helm
helm upgrade prod-apache apache-helm -n prod-apache

#### Rollback with Helm -
helm rollback prod-apache 1 -n prod-apache
