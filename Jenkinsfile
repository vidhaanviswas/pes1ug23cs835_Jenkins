pipeline {
    agent any

    environment {
        SRN = "YOUR_SRN-1"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Starting the build process...'
                // Intentional Error: Invalid command
                sh '''
                cd main
                g++ invalid_file.cpp -o $SRN
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
