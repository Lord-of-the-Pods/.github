Message from LORD OF THE PODS :

Hello Pinions , 
This Project Aims the explorers of Cloud Native Technologies . 
We want to learn the concepts of the following technologies & concepts :

1. Kubernetes - K8s on minikube 
2. Development of Microservices using Springboot & Quarkus [JAVA]
3. Concepts of EIP's [Enterprise Integration Patterns] using Apache Camel Integration
4. Concepts of MOM [Message oriented Middleware] using 
5. Continous Deployments of the above mentioned microservices over K8s using Tekton Pipelines
6. Gitops using ArgoCd
7. Concepts of service mesh , and application onboarding on K8s using Istio 

We will be using open source tools and technologies ,
so that everyone Pinion is cloud ready .


You can setup your own machine using the following steps : 

1. Install minikube on your local machine :

Use the Minikube documentation to install minikube .

```
https://minikube.sigs.k8s.io/docs/start/
```

2. Setup your favourite IDE to code the microservices and k8s objects :

```
https://github.com/orgs/Lord-of-the-Pods/repositories
```


3. Create the following namespaces in K8s :

CICD for your tekton pieplines
ArgoCd for your Argocd Gitops
Lotp for your microservices

```
kubectl create namespace cicd            

kubectl create namespace lotp

kubectl create namespace argocd
```


4. Install Tekton Pipelines on minikube 

```
kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml

kubectl get pods --namespace tekton-pipelines --watch
```

5. Install Tekton Dashboard on minikube
```
kubectl apply --filename https://storage.googleapis.com/tekton-releases/dashboard/latest/release.yaml

kubectl get pods --namespace tekton-pipelines --watch
```

6. Access Tekton
```
kubectl -n argocd port-forward svc/argocd-server 9001:443
```

7. Install Argo CD on minikube 
```
git clone https://github.com/argoproj/argo-cd.git
cd ~/learning/argo/argocd/argo-cd/manifests
kubectl -n argocd apply -f install.yaml
```

8. Access Argo
```
kubectl --namespace tekton-pipelines port-forward svc/tekton-dashboard 9097:9097
```



