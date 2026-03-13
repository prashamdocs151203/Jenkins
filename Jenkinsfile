pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run ML Application') {
            steps {
                echo 'Running ML app...'
                sh 'python app.py'
            }
        }

        stage('Test API') {
            steps {
                echo 'Testing API...'
                sh 'pytest'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed!'
        }
    }
}
