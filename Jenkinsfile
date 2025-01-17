pipeline {
	agent any
	//agent { docker {image 'node:latest'}}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome:bin:$PATH"

	}
	stages {
		stage ('Build') {
			steps {
				sh "mvn --version"
				sh "docker --version"
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