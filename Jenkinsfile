pipeline {
  agent any
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

