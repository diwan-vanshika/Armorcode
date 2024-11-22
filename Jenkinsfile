pipeline {
    agent any

    environment {
        IMAGE_NAME = "armorcode-hello-world-app"
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/diwan-vanshika/Armorcode.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t $IMAGE_NAME .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run --name hello-world-container -d $IMAGE_NAME'
                }
            }
        }

        stage('Print README') {
            steps {
                script {
                    sh 'docker exec hello-world-container cat /usr/src/app/README.md'
                }
            }
        }

    }
}