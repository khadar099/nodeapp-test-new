pipeline {
    agent any
    environment {
        dockerImage = ""
        registry = "khadar099/nodeapp-test-new"
    }
    stages {
        stage('checkout source') {
            steps {
                git 'https://github.com/khadar099/nodeapp-test-new.git'
                }
            }
        stage('docker build') {
            steps {
                script {
                    dockerImage = docker.build registry
                }
            }
        }
    }
}
