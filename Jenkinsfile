pipeline {
    agent { label 'node-agent' }
    
    stages{
        stage('Code'){
            steps{
                git url: 'https://github.com/sujeetrudra0608/nodecicddemo.git', branch: 'main' 
            }
        }
        stage('Build and Test'){
            steps{
                sh 'npm install'
                sh 'npm test'
            }
        }
        stage('Deploy'){
            steps{
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
