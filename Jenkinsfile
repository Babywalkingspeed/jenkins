pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build and Deploy') {
            steps {
                sh '''
                    cd deploy
                    docker compose down || true
                    docker compose up -d --build
                '''
            }
        }
    }
}
