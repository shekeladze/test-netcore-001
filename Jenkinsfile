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
                sh 'dotnet build Test001.sln --configuration Release --no-restore'
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
