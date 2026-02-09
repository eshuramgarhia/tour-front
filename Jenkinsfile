pipeline {
    agent any

    stages {

        stage('Git Checkout') {
            steps {
                git url: 'https://github.com/eshuramgarhia/tour-front.git',
                    branch: 'main',
                    credentialsId: 'jenkins'
            }
        }

        stage('Install') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }
    }
}

