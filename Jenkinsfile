pipeline {
    agent any

    environment {
        dockerImage = ''
    }

    stages {
        stage("Get Source Code") {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-private-key', url: 'git@github.com:shekeladze/test-netcore-001.git']]])
            }
        }
        stage("Build Docker Image") {
            steps {
                script {
                    dockerImage = docker.build registry
                }
            }
        }
        stage("test") {
            steps {
                echo 'testing the application...'
            }
        }
        stage("deploy") {
            steps {
                echo 'deploying the application...'
            }
        }
    }   
}
