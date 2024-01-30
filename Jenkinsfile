pipeline {
    agent {
        docker { image 'node:20.11.0-alpine3.19' }
    }
    
    stages {
        stage('Build') {
            steps {
                // Install dependencies
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                // Run tests (adjust as needed)
                sh 'npm test'
            }
        }
    }
}

