pipeline {
    agent any
    stages {
        stage("git checkout") {
            steps {
                git 'https://github.com/mohamedmohsen20/CI-CD.git'
            }
        }
        stage('docker build image') {
            steps {
                sh "docker build -t cicd:${BUILD_NUMBER} ."
            }
        }
        stage("deployment") {
            steps {
                sh "docker run -d -p 1000:80 cicd:${BUILD_NUMBER} "
            }
        }
    }
}