pipeline {
    environment {
        dockerImagename = "khadar099/nodeapp-test-new"
        dockerImage = ""
    }
    agent any
    stages {
        stage('checkout source') {
            steps {
                git 'https://github.com/khadar099/nodeapp-test-new.git'
                }
            }
        stage('Build docker image') {
            steps {
                script {
                    dockerImage = docker.build dockerImagename
                }
            }
        }
        stage('pushing image to dockerhub') {
            environment {
                    registryCredentials = 'dockerhublogin'
                    }
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhublogin', url: 'https://hub.docker.com') {
                        dockerImage.push("latest")
                    } 
                }
            }
        }
    }
}
