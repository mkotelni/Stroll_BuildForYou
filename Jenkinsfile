pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install npm') {
            steps {
                sh 'curl -L https://www.npmjs.com/install.sh | sh || true'
                sh 'export PATH=$HOME/.npm-global/bin:$PATH && npm --version || true'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh '''
                    export PATH=$HOME/.npm-global/bin:/usr/local/bin:$PATH
                    cd STROLLReact
                    npm install
                '''
            }
        }
        stage('Build') {
            steps {
                sh '''
                    export PATH=$HOME/.npm-global/bin:/usr/local/bin:$PATH
                    cd STROLLReact
                    npm run build
                '''
            }
        }
    }
}