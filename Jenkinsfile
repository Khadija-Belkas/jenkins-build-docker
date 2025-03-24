node {
    def app

    stage('Clone') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("xavki/nginx")
    }

    stage('Run image') {
        docker.image('xavki/nginx').withRun('-p 8090:80') { c ->
            sh 'docker ps'
            sh 'curl localhost:8090'
        }
    }
}
