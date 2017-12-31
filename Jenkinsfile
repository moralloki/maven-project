pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
              withMaven(
                // Maven installation declared in the Jenkins 
                // "Global Tool Configuration"
                maven: 'LocalApacheMaven3.5.2')

                // Run the maven build
                sh 'mvn clean package'
 
              } // steps
            
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}

