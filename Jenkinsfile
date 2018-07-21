pipeline {
    agent {
        docker { image 'php:7.0-cli' }
    }
    stages {
        stage('Test PHP') {
            steps {
                sh 'php -v'
            }
        }
    }
}