pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/TuanDung368/CICD.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('flask-app')
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh 'docker rm -f flask-container || true'
                    sh 'docker run -d -p 5000:5000 --name flask-container flask-app'
                }
            }
        }
    }
}
