pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout source code'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Build application'
                sh 'node -v'
            }
        }

        stage('Test') {
            steps {
                echo 'Running test'
                sh './scripts/test.sh'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application'
                sh './scripts/deploy.sh'
            }
        }
    }

    post {
        success {
            echo '🎉 PIPELINE SUCCESS'
        }
        failure {
            echo '❌ PIPELINE FAILED'
        }
    }
}
