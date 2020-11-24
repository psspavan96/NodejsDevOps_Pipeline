pipeline {
  environment {
    registry = "your docker registry"
    registryCredential = 'your registry credentials'
    dockerImage = ''
  }
  agent any
  tools {nodejs "Node" }
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/psspavan96/NodejsDevOps_Pipeline'
      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }  
      }
    }
    stage('Deploy Image') {
      steps{
         script {
            docker.withRegistry( '', registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }
  }
}
