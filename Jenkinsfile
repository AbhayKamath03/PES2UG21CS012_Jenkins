pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ main.cpp -o output'
                echo 'Building the project...'
            }
        }
        stage('Test') {
            steps {
                // Intentionally causing the 'Test' stage to fail
                sh 'echo "Error: Testing failed" && exit 1'
                echo 'Running tests...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
            }
        }
    }

    post {
        failure {
            // Display "pipeline failed" if any of the stages fail
            error 'Pipeline failed'
        }
    }
}
