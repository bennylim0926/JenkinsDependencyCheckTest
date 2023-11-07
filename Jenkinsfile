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
				dependencyCheck additionalArguments: '--format HTML --format XML' --suppression suppression.xml, odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}