pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('VERCEL_TOKEN') // Use Jenkins credentials ID
    }

    stages {
        stage('Install Node.js dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test React App') {
            steps {
                bat 'npm test -- --watchAll=false'
            }
        }

        stage('Build React App') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Deploy to Vercel') {
            steps {
                bat 'vercel --token %VERCEL_TOKEN% --prod'
            }
        }
    }
}
