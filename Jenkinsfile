pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'cd /home/ubuntu/devops-project && docker build -t devops-project .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop devops-container || true'
                sh 'docker rm devops-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 80:80 --name devops-container devops-project'
            }
        }
    }
}
