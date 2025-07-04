pipeline {
    agent any
    environment {
        DOCKER_IMAGE = 'my-flask-app'
    }
    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/TuanDung368/CICD.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image using the docker plugin
                    docker.build("${DOCKER_IMAGE}")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    // Run the container
                    docker.image("${DOCKER_IMAGE}").run("-p 5000:5000")
                }
            }
        }
    }
}
