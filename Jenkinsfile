pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git '/home/Desktop/SIT Stuff/Y3T1/3203 - Secure Software Dev/labs/x06/JenkinsDependencyCheckTest'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML' --suppression suppression.xml, odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}