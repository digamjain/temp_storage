node {
    def app

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("digamjain/temp_storage")
    }
    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker_id') {
            app.push("${env.BUILD_NUMBER}")
        }
    }
}
