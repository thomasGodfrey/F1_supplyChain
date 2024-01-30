pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'myjenkins-blueocean'
                    // Run the container on the node specified at the
                    // top-level of the Pipeline, in the same workspace,
                    // rather than on a new node entirely:
                    reuseNode true
                }
            }
            steps {
                sh 'gradle --version'
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
}