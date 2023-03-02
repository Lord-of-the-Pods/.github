```
kubectl create namespace cicd            

kubectl create namespace lotp

kubectl create namespace argocd

// Install Tekton Pipelines on minikube 

kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml

kubectl get pods --namespace tekton-pipelines --watch

// Install Tekton Dashboard on minikube

kubectl apply --filename https://storage.googleapis.com/tekton-releases/dashboard/latest/release.yaml

kubectl get pods --namespace tekton-pipelines --watch


// INstall Argo CD on minikube 

git clone https://github.com/argoproj/argo-cd.git

cd ~/learning/argo/argocd/argo-cd/manifests

kubectl -n argocd apply -f install.yaml


kubectl port-forward svc/argocd-server -n argocd 9001:443
```



```
Access Tekton



Access Argo
```
