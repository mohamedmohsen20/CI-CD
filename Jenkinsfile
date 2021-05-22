pipeline {
    agent any
    stages {
        stage("git checkout") {
            steps {
                git 'https://github.com/mohamedmohsen20/CI-CD.git'
            }
        }
        stage('docker build image') {
            sh "docker build -t cicd:${BUILD_NUMBER} ."
        }
    }
}