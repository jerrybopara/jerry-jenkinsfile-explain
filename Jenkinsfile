pipeline {
    agent {
        docker { image 'node:16-alpine' }
    }
    stages{
        stage('Check Node Version') {
            steps{
                sh 'node --version' 
            }
        }

    }
}