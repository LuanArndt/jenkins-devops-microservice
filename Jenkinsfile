pipeline {
	agent any
	//agent { docker {image 'node:latest'}}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"

	}
	stages {
		stage ('Checkout') {
			steps {
				sh "mvn --version"
				sh "docker --version"
			}
		}
		stage ('Compile'){
			steps {
				sh "mvn clean compile"
			}
		}
		stage ('Test') {
			steps {
				sh "mvn test"
			}
		}
		stage ('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
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