pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    withNodejs('NodeJS 18') {
                        sh 'npm install'
                    }
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    withNodejs('NodeJS 18') {
                        sh 'npm test'
                    }
                }
            }
        }

        stage('Lint') {
            steps {
                script {
                    withNodejs('NodeJS 18') {
                        sh 'npm run lint'
                    }
                }
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

