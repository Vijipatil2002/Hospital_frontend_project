// Jenkinsfile (CD Pipeline in release branch)
pipeline {
    agent any
    
    stages {
        stage('CD: Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to Staging'
                }
            }
        }

        stage('CD: Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to Production'
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment completed successfully!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
