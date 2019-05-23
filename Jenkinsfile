pipeline
{
   agent any
   tools
   {
      maven 'MVN'
   }
   stages
   {
      stage('Git Clone')
      {
         steps
         {
           git branch: 'declarative', url: 'https://github.com/Gauri160/JenkinsSir.git'
          }
      }
      
      stage('Maven inmstall')
      {
         steps
         {
               sh label: '', script: 'mvn clean install'
          }
      }
      
   }
}
            
