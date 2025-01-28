pipeline {
    agent { docker { image 'node:22.13.1-alpine3.21' } }
    environment {
        DOCKER_HOST= 'unix:///home/wojtek/.docker/desktop/docker-cli.sock'
    }
    stages {
        stage('build') {
            steps {
                sh 'echo "Siema ciule "'
                sh 'npm install --force'
                sh 'npm run build'

            }
        }
    }
}