pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git url: 'https://github.com/eshuramgarhia/tour-front.git',
                    branch: 'main',
                    credentialsId: 'jenkins'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build Frontend') {
            steps {
                bat 'set CI=false && npm run build'
            }
        }
    }
}

