pipeline{
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel-token')

    }

    stage('Install Node.js') {
            steps {
                // Run npm install using Windows CMD
                bat 'npm install'
            }
        }

        stage('Test React App') {
            steps {
                // Run React tests
                bat 'npm test -- --watchAll=false'
            }
        }
        
        stage('Build React App') {
            steps {
                // Run React build
                bat 'npm run build'
            }
        }

        stage('Deploy to Vercel') {
            steps {
                // Login to Vercel CLI using token (set as Jenkins secret)
                bat 'vercel --token %VERCEL_TOKEN% --prod'
            }
        }
    
}