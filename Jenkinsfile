pipeline {
    agent any

    stages {
        stage('Build docker image') {
            steps {
                bat 'docker build -t uabd-devops .'
            }
        }

        stage('Tag docker image') {
            steps {
                bat 'docker tag uadb-devops malicksn/uadb-devops:v1'
            }
        }
        stage('List docker images') {
            steps {
                bat 'docker images'
            }
        }
    }
}