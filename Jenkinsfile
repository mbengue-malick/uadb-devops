pipeline {
    def uadb-devops
    stages {
        stage('Build Docker Image') {
            agent { label 'dind-agent' }
            steps {
                uadb-devops = docker.build('malicksn/uadb-devops:v1')
            }
        }

        stage('Push Docker Image') {
            agent { label 'dind-agent' }
            steps {
                uadb-devops.push()
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
