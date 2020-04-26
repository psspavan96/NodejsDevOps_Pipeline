pipeline {
  agent any
    
  tools {nodejs "Node"}
    
  stages {
        
    stage('Cloning Git') {
      steps {
        git 'https://github.com/psspavan96/NodejsDevOps_Pipeline'
      }
    }
    stage('Install request dependency') {
      steps {
        sh 'npm install request --save'
      }
    }
        
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
    stage('Start App') {
      steps {
        sh 'npm start'
      }
    } 
 
  }
}
