pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://shaiksameer3909:Shaiksameer/3909@github.com/ShaikMohammedSameer3903/NEW-Farmapp.git'
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
            bat 'docker-compose ps'
        }
    }
}
