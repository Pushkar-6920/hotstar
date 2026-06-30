# Hotstar Clone DevOps Deployment Project

Architecture:

Developer
|
GitHub
|
Jenkins EC2
|
Docker Build
|
SonarQube
|
Trivy Scan
|
DockerHub
|
AWS EKS Kubernetes
|
Hotstar Application


Tools:

- AWS EC2
- Jenkins
- Docker
- Kubernetes
- AWS EKS
- SonarQube
- Trivy


Deployment:

1. Create EKS:

eksctl create cluster -f eks-cluster.yaml


2. Deploy:

kubectl apply -f k8s/


3. Check:

kubectl get pods -n hotstar

kubectl get svc -n hotstar
