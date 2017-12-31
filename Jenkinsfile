pipeline {
  agent any
  tools {
    maven 'LocalApacheMaven3.5.2'
  }
  stages {
    stage ('Build') {
      steps {
        sh '''
           printenv
         '''
      }
    }

    stage ('Post') {
      steps {
        echo "This is the post stage"
      }
    }
  }
}

