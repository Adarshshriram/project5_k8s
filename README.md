
# Kubernetes Minikube Project - Deploy and Manage Apps

## Objective
Deploy and manage applications locally in Kubernetes using **Minikube**, **kubectl**, and **Docker**.

---

## Tools Used
- **Minikube** - Local Kubernetes cluster
- **kubectl** - Kubernetes command-line tool
- **Docker** - Container runtime

---

## Project Deliverables
- `deployment.yaml` → Defines the application deployment.
- `service.yaml` → Exposes the application via NodePort.
- **Screenshots** of pods and services.
- Step-by-step documentation.

---

## screen Shots


# minicube installation 

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/5a7ee21c-50ef-462d-88ec-306061da9116" />

# kubectl pods

<img width="940" height="511" alt="image" src="https://github.com/user-attachments/assets/2881632b-248f-476a-9b32-ec8ee16ad597" />

# kubectl logs

<img width="940" height="573" alt="image" src="https://github.com/user-attachments/assets/52da9aa9-fd6c-420a-bc2b-3b89b2a27ef7" />

# kubectl describes

<img width="940" height="554" alt="image" src="https://github.com/user-attachments/assets/9d1ba0b0-7510-4a90-a25f-978ae737ec1b" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/5f755876-4fda-4275-94c1-acb39f01eb3a" />

# kubectl pods and services

<img width="940" height="300" alt="image" src="https://github.com/user-attachments/assets/4089fe06-6e70-41ca-8d02-dda74be2fbe5" />

## Outcome

By completing this project, you will understand:

Deploying apps in Kubernetes using Minikube.
Managing deployments and services.
Scaling and debugging Kubernetes workloads.

Steps to Run the Project

 **1. Install Docker**
```bash
sudo yum update -y
sudo yum install -y docker
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker ec2-user
newgrp docker
docker run --rm hello-world

** 2. Install kubectl **

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
kubectl version --client

** 3. Install Minikube **

cd /tmp
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube version

** 4. Start Minikube **

minikube start --driver=docker --memory=4096 --cpus=2
minikube status
kubectl get nodes

** 5. Deploy the App **

kubectl apply -f deployment.yaml
kubectl apply -f service.yaml


** 6. Verify Deployment **

kubectl get pods
kubectl get svc

** 7. Access Application **

minikube service hello-service --url

** 8. Scaling the App ** 

kubectl scale deployment hello-deployment --replicas=4
kubectl get pods

** 9. Logs & Debugging **
 
kubectl logs <pod-name>
kubectl describe pod <pod-name>

