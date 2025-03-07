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
                    checkout scm // This will checkout the code from the Git repository
                }
            }
        }

        stage('CI: Install Dependencies') {
            steps {
                script {
                    echo 'Installing dependencies'
                }
            }
        }

        stage('CI: Run Tests') {
            steps {
                script {
                    echo 'Running tests'
                }
            }
        }
    }

    post {
        success {
            echo 'CI pipeline success'
            build job: 'multibranchcicd', parameters: [
                string(name: 'BRANCH_NAME', value: 'main') // Assuming you want to trigger the CD pipeline for the 'release' branch
            ], wait: true
        }

        failure {
            echo 'CI pipeline failed. CD pipeline will not run.'
        }
    }
}
