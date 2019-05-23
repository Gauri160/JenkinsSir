pipeline
{
   agent any
   stages
   {
      stage('Compile Stage')
      {
         steps
         {
            withMaven(maven : 'MVN')
            {
               sh 'mvn clean install'
            }
         }
      }
      
      stage('Testing stage')
      {
         steps
         {
            withMaven(maven : 'MVN')
            {
               sh 'mvn test'
            }
         }
      }
      
      stage('Deploy')
      {
         steps
         { 
            sh 'scp /root/.jenkins/workspace/Decl_pipeline/in28minutes-web-servlet-jsp/target root@172.31.22.170:/opt/apache-tomcat-7.0.94/webapps'
         }
      }
   }
            
