pipeline {
    agent {
        docker {
            image 'docker:19.03' // or any appropriate Docker image version
            args '-v /var/run/docker.sock:/var/run/docker.sock'
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
                sh 'docker pull node:14'
                sh 'docker run --rm -v $PWD:/workspace -w /workspace node:14 npm install'
            }
        }
        
        stage('Test') {
            steps {
                sh 'docker run --rm -v $PWD:/workspace -w /workspace node:14 npm test'
            }
        }
        
        stage('Build') {
            steps {
                sh 'docker run --rm -v $PWD:/workspace -w /workspace node:14 npm run build'
            }
        }
    }
}
