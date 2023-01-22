pipeline {
	agent any
	// agent { docker { image 'maven:3.8.7'}}
	// agent { docker { image 'node:19.4.0'}}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHOME/bin:$mavenHome/bin:$PATH"

	}
	stages {
		stage ('Checkout') {
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
		// stage ('Compile') {
		// 	steps {
		// 		sh "mvn clean compile"
		// 	}
		// }
		// stage ('Test') {
		// 	steps {
		// 		sh "mvn Test"
		//	}
		// }
		// stage ('Intergration Test ') {
		//		steps {
		//			sh "mvn failsafe:intergration-test failsafe:verify"
		//		}
		//	}	
		// stage ('Package') {
		// 	steps {
		// 		sh "mvn package -DskipTests"
		// 	}
		// }
		stage ('Build Docker Image') {
			steps {
			//	"docker build -t ichancetek/currency-exchange-devops:$env.BUILD_TAG"
			    script {
					dockerImage = docker.build ("ichancetek/currency-exchange-devops:${env.BUILD_TAG}")
				}

			}
		}	

		stage ('Push Docker Image') {
			steps {
				script {
					docker.withRegistry('', dockerhub) {
					dockerImage.push();
					dockerImage.push('latest')
				}
				}
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












