pipeline{
	agent any
		stages {
			stage('Build') {
				steps {
					echo "Build"
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
		}
}

