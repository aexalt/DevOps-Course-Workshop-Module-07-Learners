pipeline {
    agent any

    stages {
        stage('dotnet') {
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
