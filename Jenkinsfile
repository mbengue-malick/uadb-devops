pipeline {
    agent {
        dockerContainer {
            image 'docker:26.1.4'  // Use a Docker image with Docker CLI
        }
    }
    stages {
        stage('Test') {
            steps {
                sh 'docker --version'
            }
        }
    }
}