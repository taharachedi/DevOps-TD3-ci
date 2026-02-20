pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Node.js') {
            steps {
                // Installer Node.js via Node Version Manager (ou vérifier si déjà installé)
                sh 'apt-get update && apt-get install -y nodejs npm'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build (Simulated)') {
            steps {
                echo 'Build étape simulée (pas de Docker)'
            }
        }

        stage('Deploy (Simulated)') {
            steps {
                echo 'Deploy étape simulée'
            }
        }
    }
}