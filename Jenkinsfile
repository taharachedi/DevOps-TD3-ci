pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                // Exécuter npm install dans un container Node.js
                sh 'docker run --rm -v $PWD:/app -w /app node:20 npm install'
            }
        }

        stage('Run Tests') {
            steps {
                // Exécuter npm test dans le container Node.js
                sh 'docker run --rm -v $PWD:/app -w /app node:20 npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'echo "Simulating docker build..."'
                // Tu peux décommenter la ligne suivante si tu veux vraiment builder :
                // sh 'docker build -t my-node-app .'
            }
        }

        stage('Deploy (Simulated)') {
            steps {
                sh 'echo "Simulating deploy..."'
            }
        }
    }
}