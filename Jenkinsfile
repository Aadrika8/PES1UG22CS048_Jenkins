pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ main.cpp -o YOUR_SRN-1'
            }
        }

        stage('Test') {
            steps {
                sh './YOUR_SRN-1'
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
