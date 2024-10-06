pipeline {
    agent none
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    bat 'docker images'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    uadbDevops.push()
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml -f service.yaml'
            }
        }
    }
}
