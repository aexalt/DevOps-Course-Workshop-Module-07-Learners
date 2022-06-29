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
                sh 'dotnet test'
            }
        }
        stage('typescript') {
            agent {
                docker {
                    image 'node:17-bullseye'
                }
            }
            steps {
                echo 'ts build'
                dir("DotnetTemplate.Web"){
                    sh 'npm install'
                    sh 'npm run lint'
                    sh 'npm t'
                }
            }
        }
    }
}
