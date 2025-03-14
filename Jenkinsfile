pipeline {
    agent {
        docker {
            image 'node:14'
        }
    }

    stages {
        stage('Clone repository') {
            steps {
                git branch: 'main', url: 'https://github.com/<user>/<repo>.git'
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build application') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Test application') {
            steps {
                sh 'npm test'
            }
        }

        stage('Push Docker image') {
            steps {
                sh 'docker build -t my-app:latest .'
                sh 'docker push my-app:latest'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
