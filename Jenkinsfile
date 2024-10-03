pipeline {
    agent any

    stages {
        stage('Build docker image') {
            steps {
                bat 'docker build -t uadb-devops .'
            }
        }

        stage('Tag docker image') {
            steps {
                bat 'docker tag uadb-devops malicksn/uadb-devops:test'
                bat 'echo ${REGISTRY_PASSWORD}'
            }
        }
        
        stage('Build docker') {
            steps {
                bat 'echo %REGISTRY_PASSWORD% | docker login -u malicksn --password-stdin'
                bat 'docker push malicksn/uadb-devops:test'
            }
    }
    }
}