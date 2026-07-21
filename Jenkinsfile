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
}