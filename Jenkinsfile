pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                // ✅ Clone your actual GitHub repository from main branch
                git branch: 'main', url: 'https://github.com/mahaklashkary19/W-app.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the Weather App...'
                // Example for Node.js project
                // sh 'npm install'

                // Example for Python project
                // bat 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Example for Node.js
                // sh 'npm test'

                // Example for Python
                // bat 'pytest'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Weather App...'
                // Here you can add commands to copy files or run your app locally
                // Example for Node.js:
                // sh 'npm start'
                // Example for Python:
                // bat 'python app.py'
            }
        }
    }

    post {
        success {
            echo '✅ Build Successful! Weather App pipeline completed.'
        }
        failure {
            echo '❌ Build Failed. Please check the logs for details.'
        }
    }
}
