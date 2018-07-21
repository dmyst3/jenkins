pipeline {
    agent any
    stages {
        stage('Test') {
            agent {
                docker { image 'node:7-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}