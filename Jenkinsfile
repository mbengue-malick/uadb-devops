pipeline {
agent any

    stages {
        stage('Build Docker Image') {
            agent { label 'ci_agent' }
            steps {
                script {
                    docker.build('malicksn/uadb-devops:v1')
                }
            }
        }

        stage('Push Docker Image') {
            agent { label 'ci_agent' }
            steps {
                script {
                    docker.push('malicksn/uadb-devops:v1')
                }
            }
        }
    }

}
