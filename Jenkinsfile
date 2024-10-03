pipeline {
    agent {
        dockerContainer {
            image 'docker:24.0.5'  // Use a Docker image with Docker CLI
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