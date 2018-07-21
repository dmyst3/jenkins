pipeline {
    agent any
    stages {
        stage('Test Node') {
            agent {
                docker { image 'node:7-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
        stage('Test Python') {
            agent {
                docker { image 'python:3' }
            }
            steps {
                sh 'python -v'
            }
        }
    }
}