pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build 'PES2UG21CS012-1'
                sh 'g++ main.cpp -o output '
		echo 'Building the project...'
            }
        }
        stage('Test') {
            steps {
                sh './output'
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
            error 'pipeline failed'
        }
    }
}
