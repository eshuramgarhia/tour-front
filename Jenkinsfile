pipeline {
    agent any

    environment {
        NODE_ENV = 'production'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'YOUR_GITHUB_REPO_URL'
            }
        }

        stage('Install Backend Dependencies') {
            steps {
                dir('tour_and_travel_mern-main') {
                    sh 'npm install'
                }
            }
        }

        stage('Build Frontend') {
            steps {
                dir('tour_and_travel_mern-main') {
                    sh 'npm run build'
                }
            }
        }

        stage('Start App with PM2') {
            steps {
                dir('tour_and_travel_mern-main') {
                    sh '''
                    pm2 delete tour-app || true
                    pm2 start index.js --name tour-app
                    pm2 save
                    '''
                }
            }
        }
    }
}
