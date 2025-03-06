// Jenkinsfile (CI Pipeline in main branch)
pipeline {
    agent any
    environment {
        NODE_ENV = 'production'
    }

    stages {
        stage('CI: Checkout') {
            steps {
                script {
                    echo 'Checking out the code'
                    checkout scm
                }
            }
        }

        stage('CI: Install Dependencies') {
            steps {
                script {
                    echo 'Installing dependencies'
                    sh 'npm install'
                }
            }
        }

        stage('CI: Run Tests') {
            steps {
                script {
                    echo 'Running tests'
                    sh 'npm test'
                }
            }
        }

        stage('CI: Linting') {
            steps {
                script {
                    echo 'Running linting'
                    sh 'npm run lint'
                }
            }
        }
    }

    post {
        success {
            echo 'CI pipeline completed successfully. Triggering CD pipeline...'
            // Trigger CD pipeline in the release branch after CI succeeds
            build job: 'CI_CD_Pipeline', parameters: [
                string(name: 'BRANCH_NAME', value: 'release')
            ], wait: false
        }

        failure {
            echo 'CI pipeline failed. CD pipeline will not run.'
        }
    }
}
