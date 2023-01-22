pipeline {
	agent any
	// agent { docker { image 'maven:3.6.3'}}
	// agent { docker { image 'node:19.4.0'}}
	enviroment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHOME/bin:$mavenHome/bin:$PATH"

	}
	stages {
		stage ('Build') {
			steps {
				sh 'mvn --version'
				 sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
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












