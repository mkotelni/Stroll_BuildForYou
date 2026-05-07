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
                sh '''
                    curl -fsSL https://registry.npmjs.org/npm/-/npm-10.8.2.tgz | tar -xz
                    mv package npm-local
                '''
            }
        }
        stage('Install Dependencies') {
            steps {
                sh '''
                    cd STROLLReact
                    node ../npm-local/bin/npm-cli.js install
                '''
            }
        }
        stage('Build') {
	    steps {
        	sh '''
            	cd STROLLReact
            	node ../npm-local/bin/npm-cli.js install
	            node ../npm-local/bin/npx-cli.js tsc --noEmit
        	'''
    	    }
	}	
    }
}