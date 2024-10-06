pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t malicksn/uadb-devops:v3 .'
                // script {
                //     uadbDevops = docker.build('malicksn/uadb-devops:v2')
                // }
            }
        }

        stage('Push Docker Image') {
            steps {
                
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                bat 'docker push malicksn/uadb-devops:v2'
        }
                    // uadbDevops.push()
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
