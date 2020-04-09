pipeline{
  agent any
  tools {
        maven 'maven-3.6.3'
    }
  stages{
   stage("build"){
    steps{
      echo 'building the application...'
      sh 'mvn clean compile package'
      echo 'application built...'
     }
     
    stage("test"){
     steps{
      echo 'testing the application...'
      sh 'mvn test' 
     }     
    stage("deploy"){
     steps{
      echo 'deploying the application...'
     }
   }
  }
}
