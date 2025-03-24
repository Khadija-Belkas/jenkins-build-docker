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
        container = docker.image('xavki/nginx').run('-p 8097:80')
        bat 'docker ps'
        bat 'curl http://localhost:8097'
    }
    }
