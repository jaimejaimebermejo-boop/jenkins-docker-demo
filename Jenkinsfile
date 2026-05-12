pipeline {
    agent {
        label 'DOTNETCORE'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build ConsoleApp1/ConsoleApp1.csproj'
            }
        }
    }
}