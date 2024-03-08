pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
		build 'PES2UG21CS012-1'
		sh 'g++ ./main/hello.cpp'
                echo 'Building the project...'
            }
        }

        stage('Test') {
            steps {
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
        always {
            echo 'Pipeline completed'

            script {
                // Check if any of the previous stages failed
                if (currentBuild.resultIsBetterOrEqualTo('FAILURE')) {
                    echo 'Pipeline failed'
                }
            } 
	      }
    } 
}
