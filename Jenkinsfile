pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-cicd:v1 .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop cicd-container || true'
                sh 'docker rm cicd-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d --name cicd-container -p 5000:5000 jenkins-cicd:v1'
            }
        }
    }
}

