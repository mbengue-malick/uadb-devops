pipeline {
	agent any

	stages {
		stage('Test github'){
		steps{
			script {
				bat 'echo Bonjour uadb'	
			}
		}
		}

	stage('docker') {
		steps {
		script { 
			bat 'docker build -t app:dev .'
			bat 'docker tag app:dev malicksn/app:dev'
			}
		}
	}
}

}
