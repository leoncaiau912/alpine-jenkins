pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t leoncaiau912/jenkins-alpine:lts .'
            }
        }
        stage('Push to dockerhub') {
            steps {
                sh 'docker push leoncaiau912/jenkins-alpine:lts'
            }
        }
    }
}
