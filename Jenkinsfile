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
    stage ('Deploy to Staging') {
      steps {
        build job: 'deploy-to-staging'
      }
    } // stage ('Deply to Staging')
    stage ('Deploy to Production') {
      steps {
        timeout(time:5, unit:'DAYS') {
          input message: 'Approve PRODUCTION deployment?'
        }
        build job: 'deploy-to-production'
      }
      post {
        success {
          echo 'Code deployed to production.'
        }
        failure {
          echo 'Deployment failed.'
        }
      }
    } // stage ('Deply to Production')
  } // stages
} // pipeline
