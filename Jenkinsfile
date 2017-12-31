pipeline {
  agent any
  tools {
    maven 'LocalApacheMaven3.5.2'
  } // tools
  stages {
    stage ('Build') {
      steps {
        // Run the maven build
        sh 'mvn clean package'
      }
      post {
        success {
          echo 'Now Archiving...'
          archiveArtifacts artifacts: '**/target/*.war'
        } // success - post
      } // post
    } // stage ('Build')
  } // stages
} // pipeline
