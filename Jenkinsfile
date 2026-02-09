
pipeline {
    agent any

    tools {
        nodejs 'NodeJS'   // Jenkins → Global Tool Configuration ch jo NodeJS name aa
    }

    stages {

        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build Frontend') {
            steps {
                bat '''
                set CI=false
                set NODE_OPTIONS=--max_old_space_size=4096
                npm run build
                '''
            }
        }
    }

    post {
        success {
            echo '✅ Build successful'
        }
        failure {
            echo '❌ Build failed'
        }
    }
}
