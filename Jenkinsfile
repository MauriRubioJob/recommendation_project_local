pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }
        stage('Test') {
            steps {
                sh 'python -m pytest tests/'
            }
        }
        stage('Deploy') {
            steps {
                sh 'kubectl apply -f k8s-deployment.yaml'
            }
        }
    }
}