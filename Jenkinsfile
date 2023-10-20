pipeline {
    agent { label 'node-agent' }
     
  stages {
        
    stage('Cloning Git') {
      steps {
                git url: 'https://github.com/sujeetrudra0608/nodecicddemo.git', branch: 'main' 
            }
    }
        
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
     
    stage('Test') {
      steps {
         sh 'npm test'
      }
    }      
  }
}
