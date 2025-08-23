pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/ShaikMohammedSameer3903/NEW-Farmapp.git'
            }
        }

        stage('Build & Run with Docker Compose') {
            steps {
                bat '''
                    docker-compose down
                    docker-compose build
                    docker-compose up -d
                '''
            }
        }
    }

    post {
        always {
            // Changed sh to bat for Windows compatibility
            bat 'docker-compose ps'
        }
    }
}