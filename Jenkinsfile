node {
	def app

	stage('Clone repository') {
		checkout scm
	}

	stage('Build image') {
		app = docker.build('trinsch/example-app')
	}

	stage('Push image') {
		docker.withRegistry('registry.hub.docker.com', 'docker-hub-credentials') {
			app.push('latest')
		}
	}
}
