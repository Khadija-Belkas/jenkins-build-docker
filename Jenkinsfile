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
        container = docker.image('xavki/nginx').run('-p 8095:80')
        containerId = container.getId()
        bat 'docker ps'
        bat 'curl http://localhost:8095'
    }

    stage('Stop container') {
        bat 'for /f %%i in ("docker ps -q -f "ancestor=xavki/nginx"") do docker stop %%i'
    }

    }
