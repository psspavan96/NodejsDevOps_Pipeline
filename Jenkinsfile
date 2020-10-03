pipeline {
  agent any
  environment {
    PROJECT_ID = 'jenkins1-290810' 
    CLUSTER_NAME = 'cluster-1' 
    LOCATION = 'europe-west1-b' 
    CREDENTIALS_ID = 'Jenkins1'
    registry = "pavan96/nodeapp"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent any
  tools {nodejs "Node" }
  stages {
    stage('Cloning Git') {
      steps {
        git 'your repository'
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
    stage('Deploy to GKE test cluster') {
      steps{
          sh "sed -i 's/hello:latest/hello:${env.BUILD_ID}/g' deployment.yaml"
          step([$class: 'KubernetesEngineBuilder', projectId: env.PROJECT_ID,clusterName: env.CLUSTER_NAME_TEST, location: env.LOCATION, manifestPattern: 'deployment.yaml', credentialsId: env.CREDENTIALS_ID, verifyDeployments: true])
        }
      }
  }  
}   
