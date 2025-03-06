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
                    sh 'npm install' // Replace this with the actual dependency installation command
                }
            }
        }

        stage('CI: Run Tests') {
            steps {
                script {
                    echo 'Running tests'
                    sh 'npm test' // Replace this with the actual test command
                }
            }
        }
    }

    post {
        success {
            echo 'CI pipeline success'
            build job: 'CI_CD_Pipeline', parameters: [
                string(name: 'BRANCH_NAME', value: 'release') // Assuming you want to trigger the CD pipeline for the 'release' branch
            ], wait: false
        }

        failure {
            echo 'CI pipeline failed. CD pipeline will not run.'
        }
    }
}
