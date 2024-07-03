pipeline {
    agent {
        docker {
            image 'node:14' // Use the appropriate Node.js version for your project
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/dineshdadisetty/node-dockerized-project.git', branch: 'main'
            }
        }
        
        stage('Install Dependencies') {
            steps {
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
