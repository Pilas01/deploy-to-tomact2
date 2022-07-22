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
       deploy adapters: [tomcat9(credentialsId: '3131a1c5-886e-4207-a3f7-f5b113410434', path: '', url: 'http://18.208.165.21:8080/')], contextPath: 'web', war: '**/*.war'
      }
     }
   }
 }
}

