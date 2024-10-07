pipeline {
agent any

    stages {
        stage('Build Docker Image') {
            agent { label 'ci_agent' }
            steps {
                script {
                    uadbDevops = docker.build('malicksn/uadb-devops:v1')
                }
            }
        }
    }

}
