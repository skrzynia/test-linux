pipeline {
    agent { docker { image 'node:22.13.1-alpine3.21' } }
    stages {
        stage('build') {
            steps {
                sh 'echo "Siema ciule "'
                sh 'npm install --save --legacy-peer-deps'
            }
        }
        stage('Deliver') {
            steps {
                sh 'chmod -R +rwx ./jenkins/scripts/deliver.sh'
                sh 'chmod -R +rwx ./jenkins/scripts/kill.sh'
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }    
    }
}