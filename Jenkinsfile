pipeline {
    agent any

    stages {
        stage('Build docker image') {
            steps {
                sh 'docker build -t uadb-devops .'
            }
        }

        stage('Tag docker image') {
            steps {
                sh 'docker tag uadb-devops malicksn/uadb-devops:test'
            }
        }
        
        stage('Build docker') {
            steps {
                sh 'echo ${REGISTRY_PASSWORD} | docker login -u malicksn --password-stdin'
                sh 'docker push malicksn/uadb-devops:test'
            }
    }
    }
}