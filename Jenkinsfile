pipeline {
  agent { label 'jenkins-agent' }
  tools {
    jdk 'java17'
    maven 'maven3'
    }
  stages
{
    stage("cleanup workspace")
    {
      steps{
        cleanWs()
          }    
    }
    stage("checkout from git")
    {
      steps{
        git branch: 'master' ,credentialsId: 'github' , url: 'https://github.com/Anuraguc/register-app.git'
          }
    }
    stage("build application")
    {
      steps
      {
        sh "mvn clean package"
      }
    }
    stage("test")
    {
      steps
      {
        sh "mvn test"
      }
    }


}
}
