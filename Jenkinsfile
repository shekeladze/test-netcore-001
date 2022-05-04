pipeline {
    agent any
    stages {
        stage("Get Source Code") {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-private-key', url: 'git@github.com:shekeladze/test-netcore-001.git']]])
            }
        }
        stage("build") {
            steps {
                echo 'building the application...'
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
