pipeline {
    agent any

    environment {
        DOCKER_HUB_CREDENTIALS = credentials('docker-hub-credentials')
        KUBE_CONFIG = credentials('k8s-config')
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/UnpredictablePrashant/learnerReportCS_backend.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                script {
                    sh "docker build -t ferocious71/learner-backend:latest ./backend"
                    sh "docker build -t ferocious71/learner-frontend:latest ./frontend"
                }
            }
        }

        stage('Push Images to Docker Hub') {
            steps {
                script {
                    sh "echo ${DOCKER_HUB_CREDENTIALS_PSW} | docker login -u ${DOCKER_HUB_CREDENTIALS_USR} --password-stdin"
                    sh "docker push ferocious71/learner-backend:latest"
                    sh "docker push ferocious71/learner-frontend:latest"
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                script {
                    sh "kubectl apply -f k8s-manifests/"
                }
            }
        }
    }
}
