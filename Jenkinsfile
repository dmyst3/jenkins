pipeline {
    agent {
        docker { image 'php:7.0-apache' }
    }
    stages {
        stage('Test PHP') {
            steps {
                sh 'php -v'
            }
        }
    }
}