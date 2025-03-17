pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o YOUR_SRN-1 hello.cpp'
                echo 'Build Stage Successful'
            }
        }

        stage('Test') {
            steps {
                sh './YOUR_SRN-1'
                echo 'Test Stage Successful'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
