pipeline
{
  agent any
  stages
  { 
      stage('ContinousDownload_Master')
    {
        steps
        {
           git 'https://github.com/IntelliqDevops/maven.git'  
        }
     }
     stage('ContinousBuild_Master')
     {
         steps
         {
             sh 'mvn package'
         }
     }
     stage('ContinousDeployment_Master')
     {
         steps
         {
              sh'scp /var/lib/jenkins/workspace/DeclarativePipeline1/webapp/target/webapp.war ubuntu@172.31.29.234:/var/lib/tomcat10/webapps/testapp.war'
         }
     }
     stage('ContinousTesting_Master')
     {
        steps
       {
          git'https://github.com/IntelliqDevops/FunctionalTesting.git'
           sh 'java -jar /var/lib/jenkins/workspace/DeclarativePipeline1/testing.jar'
       }    
     }
     stage('ContinousDelivery_Master')
     {
         steps
         {
             sh 'scp /var/lib/jenkins/workspace/DeclarativePipeline1/webapp/target/webapp.war ubuntu@172.31.19.221:/var/lib/tomcat10/webapps/prodapp.war'
         }
     }
   }
  }
