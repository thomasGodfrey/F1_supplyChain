pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
                sh 'svn --version'
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