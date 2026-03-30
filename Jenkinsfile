pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
        jdk  'Java21'
        maven 'Maven3'
    }
  stages{
      stage("Cleanup Workspace"){
              steps{
              cleanws()   
              }
      }
      stage ("checkout from SCM"){
              steps {
              git branch : 'main', credentialsId: 'github', url: 'https://github.com/SahilMohideen/register-app'  
              }
        }
      stage("Build Application"){
            steps {
        sh "mvn clean package"
        }
      }
      stage("Test Application"){
          steps{
            sh "mvn test"
        }
      }  
   }
}
