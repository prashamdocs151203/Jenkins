pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'python3 -m pip install -r requirements.txt'
            }
        }

        stage('Run ML Application') {
            steps {
                echo 'Running ML application...'
                sh 'python3 app.py'
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
