pipeline {
    agent any

    environment {
        REGISTRY_PASSWORD = credentials('REGISTRY_PASSWORD')
    }

    stages {
        stage('Build docker image') {
            agent docker {
                steps {
                bat 'docker build -t uadb-devops .'
            }
            }
            
        }

        stage('Tag docker image') {
            steps {
                bat 'docker tag uadb-devops malicksn/uadb-devops:test'
            }
        }
        
        stage('Build docker') {
            steps {
                bat 'echo ${REGISTRY_PASSWORD} | docker login -u malicksn --password-stdin'
                bat 'docker push malicksn/uadb-devops:test'
            }
    }
    }
}