pipeline {
    agent none

    environment{
        DOTNET_CLI_HOME = "/tmp/DOTNET_CLI_HOME"
    }
    stages {
        stage('dotnet') {
            agent {
                docker {
                    image 'mcr.microsoft.com/dotnet/sdk:6.0'
                }
            }
            steps {
                echo 'dotnet build'
                sh 'dotnet build'
            }
        }
        stage('typescript') {
            steps {
                echo 'ts build'
            }
        }
    }
}
