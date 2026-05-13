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
        stage('Build and Push') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhubcreds') {
                        sh '''
                            docker buildx create --use --name mybuilder || true
                            docker buildx build \
                                --platform linux/amd64,linux/arm64 \
                                -t jbdelpozo2/product-demo:jenkinsfile \
                                --push \
                                product-docker/
                        '''
                    }
                }
            }
        }
    }
}
