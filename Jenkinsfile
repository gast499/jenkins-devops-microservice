pipeline {
	agent any
	// agent { docker { image 'node:latest' } }
	tools {
		maven "MyMaven"
	}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'MyMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Build') {
			steps {
				echo "$PATH"
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
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
