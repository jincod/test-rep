node('windows') {
	stage('SCM') {
		git 'https://github.com/jincod/test-rep'
	}

	stage('SonarQube analysis') {
		def scannerHome = tool 'SonarQube Scanner 2.8';

		withSonarQubeEnv('SonarQube Server') {
			bat "${scannerHome}\\bin\\sonar-scanner -Dsonar.login=${SONAR_AUTH_TOKEN} -X"
		}
	}
}