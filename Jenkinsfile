pipeline {
    agent any
    
 stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/TuanDung368/CICD.git'
            }
        }
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    def app = docker.build("my-flask-app")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    app.run("-p 5000:5000")
                }
            }
        }
    }
}
} 
