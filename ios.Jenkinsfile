pipeline{
    agent any
    
    environment{
        appName = "test-app"
        workspace = "./test-app/test-app.xcodeproj/project.xcworkspace/"
    }

    options { 
        buildDiscarder(logRotator(numToKeepStr: '1')) 
    }

    stages{
        stage('Checkout App'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                    userRemoteConfigs: [[url: 'https://github.com/dmyst3/ios.git']]
                ])
            }
        }
        stage('Unit test App'){
            steps{
                sh 'echo unit testing skipped due no test specified'
            }
        }
        stage('Build App'){
            steps{
                script{
                    sh "xcodebuild -scheme ${env.appName} -workspace ${env.workspace}/ build CODE_SIGN_IDENTITY='' "
                }
            }
        }
        stage('Publish App'){
            steps{
                sh 'echo publish app skipped'
            }
        }
    }
    post{
        success{
            script{
                sh 'echo build successful'
            }
            
        }
        failure{
            script{
                sh 'echo build failed'
            }

        }
        aborted{
            script{
                sh 'echo build aborted'
            }

        }
        always{
            script{
                sh 'echo will allways run'
            }

        }
        cleanup{
            script{
                sh 'echo this step will clean up the pipeline'
            }
        }
    }

}