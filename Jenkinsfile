pipeline {
	agent any
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('CheckOut') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "JOB NAME- $env.JOB_NAME"
			}
		}
		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Tests') {
			steps {
				sh "mvn test"
			}
		}
		stage('Integration Tests') {
			steps {
				sh "mvn failsafe:integration-test: failsafe:verify"
			}
		}	
				
	}
		post{
			always {
				echo "I run always"
			}
			success {
				echo "I run when you are successful"
			}
			failure {
				echo "I run when the code fails"
			}
			changed {
				echo "This will run only if the state of the Pipeline has changed"
            	echo "For example, if the Pipeline was previously failing but is now successful"

			}
		}
}

