# CI/CD Pipeline for Node.js Application

This project demonstrates a full **CI/CD pipeline** for a Node.js application using:

- GitHub (source code repository)
- Jenkins (CI/CD automation)
- Docker (containerization)
- Kubernetes (deployment)

Every push to GitHub triggers Jenkins to build the Docker image, run tests, push the image to Docker Hub, and deploy the app to Kubernetes.

## Project Structure

ci-cd-pipeline/
├── src/                  # Node.js application code
│   └── app.js
├── k8s/                  # Kubernetes manifests
│   ├── deployment.yaml
│   └── service.yaml
├── Dockerfile            # Docker build instructions
├── Jenkinsfile           # Jenkins pipeline definition
├── package.json          # Node.js dependencies and scripts
├── .gitignore            # Files to exclude from Git
└── README.md             # Project documentation

## Pipeline Flow

1. Developer pushes code to GitHub  
2. Jenkins polls GitHub for changes  
3. Jenkins builds Docker image  
4. Jenkins runs tests  
5. Jenkins pushes Docker image to Docker Hub  
6. Jenkins deploys the image to Kubernetes

## Run Locally

1. Install dependencies:

```bash
npm install
```

2. Run the application:

```bash
npm start
```

3. Access the app at:

```
http://localhost:3000
```

## Docker Build

```bash
docker build -t myapp:latest .
docker run -p 3000:3000 myapp:latest
```

## Kubernetes Deployment

```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl get pods
kubectl get svc
```
