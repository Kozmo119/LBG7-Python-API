pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                docker build -t python-api .
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                python lbg.test.py
                '''
            }
        }
        stage('Clean up') {
            steps {
                sh '''
                docker-compose down
                docker-compose up -d
                '''
            }
        }
    }
}