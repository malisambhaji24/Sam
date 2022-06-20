node {
    def app
    stage('SCM')
    scm
        stage('Build image') {
        app = docker.build("sambhaji24/sam")
    }

    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
