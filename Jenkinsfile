pipeline {
    agent any
    stages {
        stage("git checkout") {
            steps {
                git 'https://github.com/mohamedmohsen20/CI-CD.git'
            }
        }
        stage('docker build image') {
            input {
                message "ENTER TAG"
                ok "yes"
                parameters {
                    string(name: 'TAG', description= 'enter TAG num')
                }
            }
            steps {
                sh "docker build -t cicd:${params.TAG} ."
            }
        }
        stage("deployment") {
            steps {
                sh "docker run -d -p 1000:80 cicd:${BUILD} "
            }
        }
    }
}