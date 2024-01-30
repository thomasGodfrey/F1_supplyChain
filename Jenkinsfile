pipeline {
    agent { docker { image 'abd2fd1439d6a14050d9235c07e31668324bb66da55b7ebbe4e3a299473572a9' } }
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