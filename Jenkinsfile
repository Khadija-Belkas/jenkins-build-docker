node {
    def app
    def container

    stage('Clone') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("xavki/nginx")
    }

    stage('Run image') {
        container = docker.image('xavki/nginx').run('-p 8091:80')
        bat 'docker ps'
        bat 'curl http://localhost:8091'
    }

    stage('Stop container') {
        bat "docker stop ${container.id}"
    }
}
