pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/saundarya-droid/nginx-html.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                sudo cp index.html /var/www/html/index.html
                sudo systemctl restart nginx
                '''
            }
        }
    }
}
