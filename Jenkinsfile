pipeline {
    agent any

    stages {

        stage('Install') {
            steps {
                bat 'call npm ci'
            }
        }

        stage('Lint') {
            steps {
                bat 'call npm run lint'
            }
        }

        stage('Test') {
            steps {
                bat 'call npm test'
            }
        }

        stage('Build') {
            steps {
                bat 'call npm run build'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'dist/**', fingerprint: true
            }
        }
    }

    post {
        success {
            echo '✅ Build Successful!'
        }

        failure {
            echo '❌ Build Failed!'
        }
    }
}