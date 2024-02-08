# Running this application

- Run the following commands after starting up minikube.

```bash
# Deploy secrets.yaml and configmap.yaml
kubectl apply -f secrets.yaml -f configmap.yaml

# Create configmap from init.sql inside cluster
kubectl create configmap mysql-init-config --from-file=init.sql

# SSH into node, create hostPath volume mount directory and exit
minikube ssh

sudo mkdir /mnt/data

exit

# Create persistent volume and persistent volume claim
kubectl apply -f todo-app-pv.yaml -f todo-app-pvc.yaml

# Deploy the deployments and services
kubectl apply -f todo-app-deployment.yaml -f todo-app-db-deployment.yaml
```
