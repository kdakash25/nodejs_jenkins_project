pipeline {
    agent { label 'docker-node' }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/kdakash25/https://github.com/kdakash25/nodejs_jenkins_project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t node-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f node-app || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:3000 --name node-app node-app'
            }
        }
    }
}
