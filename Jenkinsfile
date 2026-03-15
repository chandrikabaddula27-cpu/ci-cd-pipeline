pipeline {
    agent any
    environment {
        DOCKER_IMAGE = "856526/nodejs-cicd-app"
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/chandrikabaddula27-cpu/ci-cd-pipeline.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE:latest .'
            }
        }
        stage('Push Docker Image') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-password', variable: 'DOCKER_PASS')]) {
                    sh 'echo $DOCKER_PASS | docker login -u 856526 --password-stdin'
                    sh 'docker push $DOCKER_IMAGE:latest'
                }
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/deployment.yaml'
                sh 'kubectl apply -f k8s/service.yaml'
            }
        }
    }
}
