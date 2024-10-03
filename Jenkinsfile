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
                bat 'docker tag uadb-devops malicksn/uadb-devops:v1'
            }
        }
        
        stage('Build docker') {
            steps {
                bat 'echo ${REGISTRY_PASSWORD} | docker login -u ${REGISTRY_USER} --password-stdin'
                sh 'docker push malicksn/uadb-devops:test'
            }
    }
    }
}