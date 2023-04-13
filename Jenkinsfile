pipeline {
    agent any

    stages {
        stage('docker build') {
            steps {
                sh 'docker build -t khanshoyeb7/changed .'
            }
        }
        stage('docker push') {
            steps {
                withCredentials([string(credentialsId: 'dockerpasswd', variable: 'dhpasswd')]) {
                    sh 'docker login -u khanshoyeb7 -p ${dhpasswd}'
                    sh 'docker push khanshoyeb7/blank'
                }
            }
        }
    }
}
