pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o PES1UG22CS216-1 main.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './wrongcode'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage (Placeholder, modify as needed)'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
