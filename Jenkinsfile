node {
	stage('SonarQube analysis') {
		def scannerHome = tool 'SonarQube Scanner 2.8';

		withSonarQubeEnv('SonarQube Server') {
			bat "${scannerHome}\\bin\\sonar-scanner"
		}
	}
}