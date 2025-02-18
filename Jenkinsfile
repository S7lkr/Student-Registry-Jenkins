pipeline {
    agent any
    stages {
        stage('Install dependencies') {
            steps {
                // Commands to build
                bat 'npm install'
            }
        }
        stage('Run integration tests') {
            steps {
                // Commands to build
                bat 'npm run test'
            }
        }
    }
}