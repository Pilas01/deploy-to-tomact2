pipeline {
  agent any
  tools {
    maven 'Maven' 
       }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean install -DskipTest'
      }
    }
    stage ('Deploy To Tomcat Server') {
      steps{
        script {
        deploy adapters: [tomcat9(credentialsId: '0b095661-1050-4343-a005-13e208b242e3', path: '', url: 'http://18.208.165.21:8080/')], contextPath: 'web', war: '**/*.war'
      }
     }
   }
 }
}

