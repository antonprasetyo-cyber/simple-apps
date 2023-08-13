pipeline {
    agent {
        node {
            label 'devops1'
        }
    }
    stages {
        stage('Build Apps') {
            steps {
                sh 'npm install'
            }
        }
        stage('Testing') {
            steps {
                sh '''npm test
                npm run test:coverage'''
            }
        }
        stage('Scanning Code') {
            steps {
                sh'''
                sonar-scanner   -Dsonar.projectKey=training-devops   -Dsonar.sources=.   -Dsonar.host.url=http://10.23.2.1:9000   -Dsonar.login=sqp_4eb06faac0125227a16b059d696f3ce3201ca84f
                '''
            }
        }
        stage('Build Image') {
            steps {
                sh '''
                docker compose build
                '''
            }
        }
        stage('Deploy Apps') {
            steps {
                sh '''
                docker compose up -d
                '''
            }
        }
        stage('Push Image') {
            steps {
                echo 'Push Image'
            }
        }

    }
}