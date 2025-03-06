// Jenkinsfile (CD Pipeline in release branch)
pipeline {
    agent any
    environment {
        NODE_ENV = 'production'
    }

    stages {
        stage('CD: Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to Staging'
                    checkout scm
                    sh 'npm run deploy:staging'  // Modify this to your staging deployment command
                }
            }
        }

        stage('CD: Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to Production'
                    checkout scm
                    sh 'npm run deploy:production'  // Modify this to your production deployment command
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
