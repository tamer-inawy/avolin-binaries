#!/usr/bin/env groovy
pipeline {
  agent { label 'avolin-tradebeam-isupply || avolin-tradebeam-linux' }
  
  options {
    timestamps()
  }
  
  stages {

    stage('test') {
      steps {
        
        nexusArtifactUploader artifacts: [
          [artifactId: 'tradebeam-isupply', classifier: '', file: "isupply-build-resources.zip", type: 'zip']
          ], credentialsId: 'central.jnk.nexus', groupId: 'avolin', nexusUrl: 'nexus.devfactory.com', nexusVersion: 'nexus3', 
          protocol: 'https', repository: "avolin-tradebeam-shared", version: "build-resources"

      }
    }
      
    
    
  }


}
