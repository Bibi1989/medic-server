pipeline {
    agent {label 'Built-In Node'}

    environment {
        DOCKERHUB_CREDENTIALS=credentials('docker-hub-credentials')
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Bibi1989/medic-server.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t bibi1989/medic-server:latest .'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push bibi1989/medic-server:latest .'
            }
        }
    }
}
