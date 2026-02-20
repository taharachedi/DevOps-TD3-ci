pipeline {
    agent {
        docker { image 'node:20' } // Utilisation d'une image Node.js
    }
    environment {
        GH_TOKEN = credentials('github-token') // Tu devras créer ce secret dans Jenkins
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/taharachedi/DevOps-TD3-ci.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm ci'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deploy GitHub Pages') {
            steps {
                sh '''
                git config --global user.email "you@example.com"
                git config --global user.name "Taha Rachedi"
                npx gh-pages -d .
                '''
            }
        }
    }
    post {
        always {
            echo 'Pipeline terminé'
        }
    }
}