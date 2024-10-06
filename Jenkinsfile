pipeline {
    agent none
    stages {
        stage('Build Docker Image') {
            agent { label 'dind-agent' }
            steps {
                script {
                    uadbDevops = docker.build('malicksn/uadb-devops:v1')
                }
            }
        }

        stage('Push Docker Image') {
            agent { label 'dind-agent' }
            steps {
                script {
                    uadbDevops.push()
                }
            }
        }

        stage('Deploy to Kubernetes') {
            agent { label 'kubectl-agent' }
            steps {
                bat 'kubectl apply -f deployment.yaml -f service.yaml'
            }
        }
    }
}
