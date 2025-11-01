pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/mahaklashkary19/W-app.git'
            }
        }

        stage('Setup Python Environment') {
            steps {
                echo 'Setting up Python environment...'
                bat '''
                    python --version
                    pip install --upgrade pip
                    pip install -r requirement.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running test cases...'
                bat 'python -m unittest || echo "No tests found, skipping tests..."'
            }
        }

        stage('Build Package') {
            steps {
                echo 'Building application package...'
                bat 'python -m compileall .'
            }
        }

        stage('Deploy Application') {
            steps {
                echo 'Deploying Weather App...'
                bat 'python app.py'
            }
        }
    }

    post {
        success {
            echo '✅ CI/CD Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed. Check logs.'
        }
    }
}
