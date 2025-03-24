node {
    def app
    def container
    def containerId

    stage('Clone') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("xavki/nginx")
    }

    stage('Run image') {
        container = docker.image('xavki/nginx').run('-p 8093:80')
        containerId = container.getId()
        bat 'docker ps'
        bat 'curl http://localhost:8093'
    }

    stage('Stop container') {
        echo "Stopping container ID: ${containerId}"
        bat "docker stop ${containerId}"
    }
}
