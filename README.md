# CI/CD Pipeline for Node.js Application

This project demonstrates a **full CI/CD pipeline** for a Node.js application using:

- **GitHub** – source code repository  
- **Jenkins** – CI/CD automation  
- **Docker** – containerization  
- **Kubernetes** – deployment  

Every push to GitHub triggers Jenkins to **build the Docker image, run tests, push the image to Docker Hub, and deploy the app to Kubernetes**, showcasing end-to-end DevOps skills.

---

## Project Structure

ci-cd-pipeline/
├── src/                  # Node.js application code
│   └── app.js
├── k8s/                  # Kubernetes manifests
│   ├── deployment.yaml
│   └── service.yaml
├── Dockerfile            # Docker build instructions
├── Jenkinsfile           # Jenkins CI/CD pipeline definition
├── package.json          # Node.js dependencies & scripts
├── package-lock.json     # Locked dependency versions
├── .gitignore            # Files to exclude from Git
└── README.md             # Project documentation

---

## Pipeline Flow

1. Developer pushes code to GitHub  
2. Jenkins polls GitHub for changes  
3. Jenkins builds Docker image  
4. Jenkins runs tests  
5. Jenkins pushes Docker image to Docker Hub  
6. Jenkins deploys the image to Kubernetes  

---

## Run Locally

Install dependencies:

```bash
npm install

Run the application:

npm start

Access the app at:

http://localhost:3000
Docker Build

Build Docker image:

docker build -t 856526/nodejs-cicd-app .

Run Docker container:

docker run -p 3000:3000 856526/nodejs-cicd-app
Kubernetes Deployment

Apply deployment and service manifests:

kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml

Check pods and service:

kubectl get pods
kubectl get svc
Key Skills Demonstrated

CI/CD Automation with Jenkins

Containerization using Docker

Orchestration & Scaling with Kubernetes

Node.js Application Development

Version Control & Collaboration with GitHub

Outcome & Learning

Built a production-ready CI/CD pipeline for Node.js applications

Integrated GitHub, Jenkins, Docker, and Kubernetes for automated deployments

Learned to scale, monitor, and manage containers efficiently
```
