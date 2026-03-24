pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/Rajan-4900/QR.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t qr .'
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh 'docker rm -f qr-container || true'
                    sh 'docker run -d -p 3000:3000 --name qr-container qr'
                }
            }
        }

    }
}