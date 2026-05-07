pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Check Tools') {
            steps {
                sh 'node --version || echo "NO NODE"'
                sh 'npm --version || echo "NO NPM"'
                sh 'which npm || echo "npm not in PATH"'
                sh 'find /usr -name "npm" 2>/dev/null'
            }
        }
    }
}