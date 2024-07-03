pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/dineshdadisetty/node-dockerized-project.git', branch: 'main'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Ensure Node.js and npm are available, either through a Docker image or installed on the agent
                sh 'npm install'
            }
        }
        
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
    }
}
