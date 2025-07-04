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
                    // Ensure that Docker is installed and available in the pipeline
                    dockerImage = docker.build("my-flask-app")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    // Running the container with port mapping
                    dockerImage.run("-p 5000:5000")
                }
            }
        }
    }
}
