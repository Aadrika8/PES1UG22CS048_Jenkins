pipeline {
    agent {
        docker {
            image 'node:14'
        }
    }
    stages {
        stage('Clone repository') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/aadrika8/YPES1UG22CS048_Jenkins.git'
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
                sh 'docker build -t pes1ug22cs048/jenkinsE:$BUILD_NUMBER .'
                sh 'docker push pes1ug22cs048/jenkins:$BUILD_NUMBER'
            }
        }
    }
}
