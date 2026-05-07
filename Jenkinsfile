pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'cd STROLLReact && npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'cd STROLLReact && npm run build'
            }
        }
    }
}
