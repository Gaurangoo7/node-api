pipeline {
    agent any
    stages {
        stage('Build and Package Node API') {
            steps {
                git '(link unavailable)'
                sh 'npm install'
                sh 'npm run build'
                sh 'docker build -t node-api .'
                sh 'docker tag node-api:latest <username>/node-api:latest'
                sh 'docker push <username>/node-api:latest'
            }
        }
        stage('Deploy Node API to Kubernetes') {
            steps {
                kubectl 'apply -f manifest.yaml'
            }
        }
    }
}
