pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'g++ -o output YOUR_SRN.cpp' // Introduce an error by misspelling 'g++'
            }
        }
        stage('Test') {
            steps {
                sh './output' 
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed!'
        }
    }
}
