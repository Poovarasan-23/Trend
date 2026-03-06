pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git 'https://github.com/Poovarasan-23/Trend.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t poov23/trend-app .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push poov23/trend-app:latest'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
