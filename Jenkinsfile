pipeline {
    options {
        disableConcurrentBuilds()
    }
    agent {
        kubernetes {
            label 'jenkins-docker'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ast9501/nodejs-docs-hello-world.git'
            }
        }
        stage('Docker Build') {
            steps {
                container('docker') {
                    //docker.withRegistry(credentialsId: '343a1072-edd3-4e77-aeec-c89c82f5e2f5') {
                    sh 'docker version && docker build -t alan0415/nodejs-demo .'
                }
            }
        }
        stage ('Docker Push') {
            steps {
                container('docker') {withCredentials([
                usernamePassword(
                  credentialsId: env.DOCKER_CREDENDITIAL,
                  usernameVariable: 'REGISTRY_USER', passwordVariable: 'REGISTRY_PASS'
                )]) {
                    sh """
                    echo ${REGISTRY_PASS} | docker login https://index.docker.io/v1/ -u ${REGISTRY_USER} --password-stdin
                    docker push alan0415/nodejs-demo
                    """
                    }
                }
            }
        }
    }
}
