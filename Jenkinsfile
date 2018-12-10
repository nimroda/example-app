node {
	def app
	
	stage('Clone repository') {
		checkout scm	
	}

	stage('Build image') {
		app = docker.build("my_image")
        }  

	stage('Push image') {
		docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
			app.push('latest')
		}
        }
}
