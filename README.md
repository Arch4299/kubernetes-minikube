# TP Kubernetes - Minikube

Ce dépôt contient le code modifié du TP Kubernetes ainsi que les configurations associées.

## Lien Docker Hub
Mon image Docker est disponible ici : `https://hub.docker.com/r/unlikeshadow/myservice`

## Commandes utilisées pour ce TP

### 1. Build et Push de l'image Docker
\`\`\`bash
docker build -t unlikeshadow/myservice:1 .
docker login
docker push unlikeshadow/myservice:1
\`\`\`

### 2. Déploiement sur Minikube
\`\`\`bash
minikube start
kubectl create deployment myservice --image=unlikeshadow/myservice:1
kubectl expose deployment myservice --type=NodePort --port=8080
\`\`\`

### 3. Vérification
\`\`\`bash
kubectl get pods
minikube service myservice --url
\`\`\`