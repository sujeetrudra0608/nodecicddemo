pipeline {
    agent any
    
    tools {nodejs "node"}
    
    stages{
        stage('Code'){
            steps{
                git url: 'https://github.com/sujeetrudra0608/nodecicddemo.git', branch: 'main' 
            }
        }
        stage('Build and Test'){
            steps{
                sh 'docker build . -t sujeetrudra0608/nodecicddemo:latest'
            }
        }
        stage('Push'){
            steps{
                // withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
        	    //  sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
                 sh 'docker push sujeetrudra0608/nodecicddemo:latest'
                //}
            }
        }
        stage('Deploy'){
            steps{
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
