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
        stage('Test Java') {
            agent {
                docker { image 'openjdk:8' }
            }
            steps {
                sh 'java --v'
            }
        }
    }
}