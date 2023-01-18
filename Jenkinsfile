pipeline {
	agent any
	Stages {
		stage ('Build') {
			steps (
				ssh "Build"
			)
		}
        stage ('Test') {
			steps (
				ssh "Test"
			)
		}
		stage ('Test Intergration') {
			steps (
				ssh "Test Intergration"
			)
		}

	}

}