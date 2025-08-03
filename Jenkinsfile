pipeline {
    agent any

    environment {
        NODE_ENV = 'test'
    }

    tools {
        nodejs "NodeJS 18" // Make sure this is configured under "Global Tool Configuration"
    }

    stages {
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

        stage('Lint') {
            steps {
                sh 'npm run lint || true'
            }
        }
    }

    post {
        success {
            echo '✅ Tests passed!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
