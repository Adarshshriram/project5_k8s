
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






