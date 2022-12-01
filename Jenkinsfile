pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                sudo docker-compose build
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                sudo docker-compose down
                sudo docker-compose up -d
                '''
            }
        }
        stage('Clean up') {
            steps {
                sh '''
                sudo docker system prune --force
                '''
            }
        }
    }
}