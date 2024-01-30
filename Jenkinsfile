pipeline {
    agent {
        docker {
            // Use the Node.js image for the build environment
            image 'node'
        }
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

        stage('Deploy') {
            steps {
                // Additional deployment steps if needed
            }
        }
    }
}
