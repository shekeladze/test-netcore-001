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
                sh 'dotnet restore WebApplication.sln'
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
