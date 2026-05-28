pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main' , url: 'https://github.com/ayush-mishraaa/devops-project-rd-infro.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t devops-project .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'sudo docker stop devops-container || true'
                sh 'sudo docker rm devops-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'sudo docker run -d -p 80:80 --name devops-container devops-project'
            }
        }
    }
}
