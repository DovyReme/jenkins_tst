pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Update package lists
                sh 'apt update'

                // Install Apache web server
                sh 'apt install -y apache2'
            }
        }

        stage('Start Apache') {
            steps {
                // Start Apache web server
                sh 'systemctl start apache2'
            }
        }
    }

    post {
        success {
            // Send a notification on success
            echo 'Apache web server started successfully!'
        }

        failure {
            // Send a notification on failure
            echo 'Failed to start Apache web server!'
        }
    }
}
