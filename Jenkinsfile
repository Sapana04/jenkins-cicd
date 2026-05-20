```groovy
pipeline {
    agent any

    stages {

        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'git@github.com:Sapana04/jenkins-cicd.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-app:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 cicd-app:v1'
            }
        }
    }
}

