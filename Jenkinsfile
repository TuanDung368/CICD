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
                script {
                    // Build Docker image
                    def app = docker.build("my-flask-app")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    // Run Docker container from the built image
                    app.run("-p 5000:5000")
                }
            }
        }
    }
}
