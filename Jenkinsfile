pipeline {
    agent any
    stages {
        stage('Install dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run security tests') {
            steps {
                bat 'npm audit'
            }
        }
        stage('Run integration tests') {
            steps {
                bat 'npm run test'
            }
        }
        stage('Deploy to STAGING') {
            steps {
                echo 'Deploying to STAGING...'
            }
        }
        stage('Approval for Production Deployment') {
            // This step will make workflow -> Cont. Delivery (manual deploy)
            steps {
                script {
                    input message: "Proceed with production deployment?", ok: 'Deploy'
                }
            }
        }
        stage('Deploy to PRODUCTION') {
            steps {
                echo 'Deploying to PRODUCTION...'
            }
        }
    }
}