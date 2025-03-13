pipeline {
    agent any  // Runs on any available Jenkins agent

    stages {
        stage('Clone Repository') {
            steps {
                checkout scm  // Checkout the latest code from GitHub
            }
        }

        stage('Build') {
            steps {
                sh 'g++ hello.cpp -o output'  // Compile the C++ program
            }
        }

        stage('Test') {
            steps {
                sh './output'  // Run the compiled program
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment successful!'  // Simulate deployment step
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'  // Display message if any stage fails
        }
    }
}
