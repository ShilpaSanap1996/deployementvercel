pipeline {
    agent any

    stages {
        stage('Install Node.js dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test React App') {
            steps {
                echo 'skip testing'
            }
        }

        stage('Build React App') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Deploy to Vercel') {
            steps {
                // Use withCredentials to pass token correctly
                withCredentials([string(credentialsId: 'VERCEL_TOKEN', variable: 'TOKEN')]) {
                    bat 'C:\\Users\\drvik\\AppData\\Roaming\\npm\\vercel.cmd --token %TOKEN% --prod'
                }
            }
        }
    }
}
