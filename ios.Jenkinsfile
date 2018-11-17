pipeline{
    agent any
    
    environment{
        appName = "test-app"
        workspace = "./test-app/test-app.xcodeproj/project.xcworkspace/"
    }
    stages{
        stage('Checkout App'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                    userRemoteConfigs: [[url: 'https://github.com/dmyst3/ios.git']]
                ])
            }
        }
        stage('Build App'){
            steps{
                script{
                    sh "xcodebuild -scheme ${env.appName} -workspace ${env.workspace}/ build CODE_SIGN_IDENTITY='' "
                }
            }
        }
    }
}