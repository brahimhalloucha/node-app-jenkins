pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'node -v'          // Optional: check Node version
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
                // Ignore lint failures if needed (use `|| true`)
                sh 'npm run lint || true'
            }
        }
    }

    post {
        failure {
            echo '❌ Build failed!'
        }
        success {
            echo '✅ Build succeeded!'
        }
    }
}
