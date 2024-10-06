pipeline {
    agent { label 'dind-agent' }  // Utiliser l'agent Docker DinD
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t my-app:latest .'
                    sh 'docker tag my-app:latest my-registry/my-app:latest'
                    sh 'docker push my-registry/my-app:latest'
                }
            }
        }
        stage('Deploy to Kubernetes') {
            agent { label 'kubectl-agent' }  // Utiliser l'agent kubectl
            steps {
                script {
                    sh 'kubectl apply -f k8s/deployment.yaml'
                }
            }
        }
    }
}
