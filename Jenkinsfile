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
        stage('Build2'){
            steps{
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            when {
                expression {"${env.GIT_BRANCH}" == "origin/master"}
            }
            steps {
                sh './node_modules/.bin/firebase deploy --token=$FIREBASE_DEPLOY_TOKEN'
            }
        }
    }
}