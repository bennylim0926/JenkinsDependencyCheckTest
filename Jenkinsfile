pipeline {
	agent any
	stages {
		// stage('Checkout SCM') {
		// 	steps {
		// 		git '/home/Documents/3x03Labs/JenkinsDependencyCheckTest'
		// 	}
		// }

		stage('OWASP Dependency-Check Vulnerabilities') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}