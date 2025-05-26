pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Duvindu3/jenkins.git'
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'  # For Node.js (or `pip install -r requirements.txt` for Python)
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'  # Runs tests (adjust for your framework)
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying to production..."'
                // Add deployment commands (e.g., `scp`, `kubectl`, `docker push`)
            }
        }
    }
    post {
        success {
            slackSend channel: '#devops', message: 'Build succeeded!'
        }
        failure {
            slackSend channel: '#devops', message: 'Build failed!'
        }
    }
}

//puka
