pipeline {
	//agent any
	agent { docker {image 'node:latest'}}
	stages {
		stage ('Build') {
			steps {
				sh "mvn --version"
			}
		}
		stage ('Test') {
			steps {
				echo "Test"
			}
		}
		stage ('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	} 
	
	post {
		always {
			echo "Post always message test"
		}
		success {
			echo "Post success message test"
		}
		failure {
			echo "Post failure message test"
		}
	}
}