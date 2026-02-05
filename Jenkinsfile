pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checkout completed'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies'
                sh 'echo "Simulate dependency install"'
            }
        }

        stage('Tests / Lint') {
            steps {
                echo 'Running tests'
                sh 'exit 0'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project'
                sh 'echo "Build successful"'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
        success {
            echo 'Pipeline succeeded'
        }
    }
}
