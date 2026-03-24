pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Rajan-4900/QR.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-image .' // 'bat' works on Windows
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