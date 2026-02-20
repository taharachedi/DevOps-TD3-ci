pipeline {
    agent {
        docker {
            image 'node:20'      // image Node.js officielle
            args '-v $HOME/.npm:/root/.npm' // pour cacher npm
        }
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
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

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-node-app . || echo "Skipping build (simu)"'
            }
        }

        stage('Deploy (Simulated)') {
            steps {
                sh 'echo "Simulating deploy..."'
            }
        }
    }
}