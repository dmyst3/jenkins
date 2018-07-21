pipeline {
    agent {
        docker { image 'php:7.0-apache' }
    }
    stages {
        stage('Checkout Code') {
            steps {
                
                //Showing php version
                sh 'php -v'

                //checking out code
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/master']], 
                    doGenerateSubmoduleConfigurations: false, 
                    extensions: [[$class: 'RelativeTargetDirectory', 
                    relativeTargetDir: 'checkout-directory']], 
                    submoduleCfg: [], 
                    userRemoteConfigs: [[url: 'https://github.com/banago/simple-php-website.git']]])
            }
        }
    }
}