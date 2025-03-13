pipeline {
    agent any  // Use any available Jenkins agent
    
    stages {
        stage('Clone repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Aadrika8/PES1UG22CS048_Jenkins.git'
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'docker run --rm -v $(pwd):/app -w /app node:14 npm install'
            }
        }

        stage('Build application') {
            steps {
                sh 'docker run --rm -v $(pwd):/app -w /app node:14 npm run build'
            }
        }

        stage('Test application') {
            steps {
                sh 'docker run --rm -v $(pwd):/app -w /app node:14 npm test'
            }
        }

        stage('Push Docker image') {
            steps {
                sh 'docker build -t pes1ug22cs048/jenkins:$BUILD_NUMBER .'
                sh 'docker push pes1ug22cs048/jenkins:$BUILD_NUMBER'
            }
        }
    }
}
