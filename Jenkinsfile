pipeline {
    agent {
        dockerContainer {
            image 'docker:24.0.5'  // Use a Docker image with Docker CLI
            args '-v /var/run/docker.sock:/var/run/docker.sock' // Bind Docker socket to access the Docker daemon
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