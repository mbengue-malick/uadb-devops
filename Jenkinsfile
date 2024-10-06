pipeline {
    agent none
    stages {
        stage('Build Docker Image') {
            agent { label 'dind-agent' }
            steps {
                script {
                    docker.build('malicksn/uadb-devops:v1').push()
                }
            }
        }
        stage('Deploy to Kubernetes') {
            agent { label 'kubectl-agent' }
            steps {
                bat 'kubectl get pods'
            }
        }
    }
}
