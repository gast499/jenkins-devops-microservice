pipeline {
	//agent any
	agent { docker { image 'node:latest' } }
	stages {
		stage('Build') {
			steps {
				sh 'node --version'
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	} 
	post {
		always {
			echo "I'm awesome.  I run always."
		}
		success {
			echo "I run when pipeline is successful."
		}
		failure {
			echo "I run when pipeline is failed."
		}
	}
}
