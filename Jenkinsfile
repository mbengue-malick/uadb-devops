pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Ici nous faisons le build du code'
            }
        }
        stage('Test') {
            steps {
                echo 'On fait un test d integration continue'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Nous deployons vers l environnment prod'
            }
        }
    }
}