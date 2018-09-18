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

                withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"

                sh 'docker push leoncaiau912/jenkins-alpine:lts'
            }
        }
    }
}
