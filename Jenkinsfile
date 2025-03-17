pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment complete!'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed!'
        }
    }
}
