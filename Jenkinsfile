pipeline {
    agent {
            label 'ubuntu'
    }

    stages {
        stage('Build') {
            steps {
                // Install Apache web server dependencies
                sh 'sudo apt update'
                sh 'sudo apt install -y apache2'
            }
        }

        stage('Start Apache') {
            steps {
                // Start Apache web server
                sh 'sudo systemctl start apache2'
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
