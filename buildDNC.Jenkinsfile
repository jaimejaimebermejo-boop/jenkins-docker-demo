def dockerImage

pipeline {
    agent {
        label 'docker'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build image') {
            steps {
                script {
                    dockerImage = docker.build("jbdelpozo2/agent-dnc:${env.BUILD_NUMBER}", 
                        "-f dotnetcore-docker/Dockerfile .")
                }
            }
        }
        stage('Push image') {
            steps {
                script {
                    docker.withRegistry('', 'dockerhubcreds') {
                        dockerImage.push()
                    }
                }
            }
        }
    }
}