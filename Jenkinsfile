pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Rushi4466/devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app:latest .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                  docker rm -f devops-app || true
                  docker run -d --name devops-app -p 5000:5000 devops-app:latest
                '''
            }
        }
    }
}
