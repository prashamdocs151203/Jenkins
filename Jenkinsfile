pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git 'https://github.com/prashamdocs151203/Jenkins.git'
            }
        }

        stage('Build & Run Containers') {
            steps {
                sh 'docker compose up --build -d'
            }
        }

        stage('Test API') {
            steps {
                sh 'curl http://localhost:5000 || true'
            }
        }

        stage('Cleanup') {
            steps {
                sh 'docker compose down'
            }
        }
    }
}
