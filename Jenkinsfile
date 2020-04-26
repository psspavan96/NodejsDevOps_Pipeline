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
 
    stage('Building image') {
       steps{
         script {
           dockerImage = docker.build dockerRegistry + ":$BUILD_NUMBER"
         }
       }
     }
     stage('Upload Image') {
       steps{
         script {
           docker.withRegistry( '', dockerRegistryCredential ) {
             dockerImage.push()
           }
         }
       }
     }
  }
}
