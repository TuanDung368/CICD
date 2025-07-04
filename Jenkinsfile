pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/TuanDung368/CICD.git'
            }
        }

        stage('Build Docker Image') {
    steps {
        sh 'docker build -t my-flask-app .'
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
