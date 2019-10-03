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
        }
        stage('Start'){
            steps{
                sh 'npm start'
            }
        }
        stage('Run test'){
            steps{
                sh 'npm run test'
            }
        }
    }
}