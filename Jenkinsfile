pipeline{
    agent {
        docker{ 
            image 'node:8-alpine'
            args '-p 3000:3000'
            }
    }
    environment {
        CI ='true'
    }
    stages {
        stage('Install'){
            steps{
                sh 'npm install'
            }
        },
        stage('Start2'){
            steps{
                sh 'npm start'
            }
        }
    }
}