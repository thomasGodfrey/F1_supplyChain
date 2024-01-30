pipeline {
    agent { docker { image 'node:20.11.0-alpine3.19' } }
    stages {
        stage('build') {
            steps {
                sh 'node --version'
            }
        }
    }
    post {
    failure {
        mail to: 'thomas.godfrey97@yahoo.com',
        subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
        body: "Something is wrong with ${env.BUILD_URL}"
    }
    success {
        mail to: 'thomas.godfrey97@yahoo.com',
        subject: "Passed Pipeline: ${currentBuild.fullDisplayName}",
        body: "All good with ${env.BUILD_URL}"                
    }
}
}