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
                // Using bat since it's Windows
                bat '''
                    docker-compose -f docker-compose.yml down
                    docker-compose -f docker-compose.yml build
                    docker-compose -f docker-compose.yml up -d
                '''
            }
        }
    }

    post {
        always {
            bat 'docker-compose -f docker-compose.yml ps'
        }
    }
}
