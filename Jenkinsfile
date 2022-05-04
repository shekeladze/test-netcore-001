pipeline {
    agent any

    stages {
        stage("Get Source Code") {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-private-key', url: 'git@github.com:shekeladze/test-netcore-001.git']]])
            }
        }
        stage("Build Docker Image") {
            steps {
                echo 'building docker image...'
                dir ('Test001.Api') {
                    sh 'docker build . '
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
