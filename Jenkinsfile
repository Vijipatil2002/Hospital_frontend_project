// Jenkinsfile (CI Pipeline in main branch)
pipeline {
    agent any
    environment {
        NODE_ENV = 'production'
    }

    stages {
        stage('CI: Checkout') {
            steps {
                
                    echo 'Checking out the code'
                
            }
        }

        stage('CI: Install Dependencies') {
            steps {
            
                    echo 'Installing dependencies'
                
            }
        }

        stage('CI: Run Tests') {
            steps {
            
                    echo 'Running tests'
                
            }
        }
        }
    }

    post {
        success {
            echo 'CI pipeline success'
            build job: 'CI_CD_Pipeline', parameters: [
                string(name: 'BRANCH_NAME', value: 'main')
            ], wait: false
        }

        failure {
            echo 'CI pipeline failed. CD pipeline will not run.'
        }
    }
}
