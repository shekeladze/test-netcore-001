pipeline {
    agent any
    stages {
        stage("init") {
            steps {
                echo 'initializing the application...'
            }
        }
        stage("build") {
            steps {
                sh 'dotnet restore Test001.sln'
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
