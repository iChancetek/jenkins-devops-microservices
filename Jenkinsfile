pipeline {
	agent any
	Stages {
		stage ('Build') {
			steps (
				sh "Build"
			)
		}
        stage ('Test') {
			steps (
				sh "Test"
			)
		}
		stage ('Test Intergration') {
			steps (
				sh "Test Intergration"
			)
		}

	}

}