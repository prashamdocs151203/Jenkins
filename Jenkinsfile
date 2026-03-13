pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo "Cloning repository..."
                git 'https://github.com/prashamdocs151203/Jenkins/new/main'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "Installing Python dependencies"
                sh 'pip install flask numpy scikit-learn'
            }
        }

        stage('Run ML Application') {
            steps {
                echo "Starting ML service"
                sh 'python ml_app.py &'
            }
        }

        stage('Test API') {
            steps {
                echo "Testing ML health endpoint"
                sh 'curl http://localhost:5002/ml/health'
            }
        }

    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
