pipeline {
    agent any

    environment {
        SRN = "PES1UG23CS835-1"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Starting the build process...'
                sh '''
                cd main
                g++ hello.cpp -o $SRN
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running the C++ application...'
                sh '''
                cd main
                ./$SRN
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application (if applicable)...'
                echo 'Deployment steps can be added here.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs for more details.'
        }
    }
}
