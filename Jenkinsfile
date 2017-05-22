node {
	stage('SCM') {
		checkout poll: false, changelog: false, scm: scm
	}

	stage('SonarQube analysis') {
		def scannerHome = tool 'SonarQube Scanner 2.8';

		withSonarQubeEnv('SonarQube Server') {
			bat "${scannerHome}\\bin\\sonar-scanner -Dsonar.login=${SONAR_AUTH_TOKEN} -Dsonar.projectVersion=1.${BUILD_NUMBER}"
		}
	}
}