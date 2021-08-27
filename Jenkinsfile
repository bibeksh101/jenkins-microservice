pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				//sh 'mvn --version'
				echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "JOB NAME- $env.JOB_NAME"
			}
		}
		stage('Tests') {
			steps {
				echo "Tests"
			}
		}
		stage('Integration Tests') {
			steps {
				echo "Integration Tests"
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

