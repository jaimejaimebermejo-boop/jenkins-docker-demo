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
                script {
                    try {
                        sh 'dotnet build ConsoleApp1/ConsoleApp1.csproj'
                    } finally {
                        archiveArtifacts artifacts: 'ConsoleApp1/**', allowEmptyArchive: true
                    }
                }
            }
        }
    }
}
