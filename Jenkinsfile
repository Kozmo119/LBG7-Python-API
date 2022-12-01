pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                docker-compose build
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                docker-compose down
                sudo docker-compose up -d
                '''
            }
        }
        stage('Clean up') {
            steps {
                sh '''
                docker system prune --force
                '''
            }
        }
    }
}