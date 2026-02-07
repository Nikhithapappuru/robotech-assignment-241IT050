pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies'
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
                echo 'Building application'
            }
        }

        stage('Simulated Deployment') {
            steps {
                echo 'Simulating deployment process'
                sh 'sleep 10'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded'
        }

        failure {
            echo 'Pipeline failed'
            sh '''
            curl -X POST \
            -H "Content-Type: application/json" \
            -d '{
              "source": "jenkins",
              "event": "pipeline_failed",
              "job_name": "'"$JOB_NAME"'",
              "build_number": "'"$BUILD_NUMBER"'"
            }' \
            https://webhook.site/0513a57c-4e78-472a-b7b2-0bb6f0547e5b
            '''
        }
    }
}

