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
                echo 'Testing'
            }
        }
        stage('Scanning Code') {
            steps {
                echo 'Scanning Code'
            }
        }
        stage('Build Image') {
            steps {
                echo 'Build Image'
            }
        }
        stage('Running Container') {
            steps {
                echo 'Running Container'
            }
        }
        stage('Push Image') {
            steps {
                echo 'Push Image'
            }
        }

    }
}