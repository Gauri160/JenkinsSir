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
            
