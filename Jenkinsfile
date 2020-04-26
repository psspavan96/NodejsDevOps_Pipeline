pipeline {
  agent any
    
  tools {nodejs "Node"}
    
  stages {
        
    stage('Cloning Git') {
      steps {
        git 'https://github.com/psspavan96/NodejsDevOps_Pipeline'
      }
    }
        
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
    stage('Install request') {
      steps {
        sh 'npm install request --save'
      }
    }
    stage('Start App') {
      steps {
        sh 'npm start'
      }
    }
      
  }
}
