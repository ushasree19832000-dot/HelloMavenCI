pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Getting code from GitHub'
                checkout scm
            }
        }

        stage('Build and Test') {
            steps {
                bat 'mvn clean verify'
            }
        }
    }

    post {
        success {
            echo 'Maven build completed successfully!'
        }
        failure {
            echo 'Build failed. Check Console Output.'
        }
    }
}