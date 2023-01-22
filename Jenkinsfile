pipeline {
	// agent any
	agent { docker { image 'maven:3.6.3'}}
	stages {
		stage ('Build') {
			steps {
				sh 'mvn --version'
				echo "Build"
			}
		}
		stage ('Test') {
			steps {
				echo "Test"
			}
		}
		stage ('Test Intergration') {
				steps {
					echo "Test Intergration"
				}
			}			
	} 
		post {
			always {
				echo 'I am awsome. I always run'
			}
			success {
				echo 'I run when you are successful'
			}
			failure {
				echo 'I run when you fail'
			}

		}
}












