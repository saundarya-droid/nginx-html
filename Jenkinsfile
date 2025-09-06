pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository using the default SCM configuration
                checkout scm
            }
        }

        stage('Deploy') {
            steps {
                // Deploy index.html to NGINX and restart the service
                sh '''
                sudo cp index.html /var/www/html/index.html
                sudo systemctl restart nginx
                '''
            }
        }
    }

    post {
        success {
            echo "Deployment completed successfully!"
        }
        failure {
            echo "Deployment failed. Check the logs."
        }
    }
}

