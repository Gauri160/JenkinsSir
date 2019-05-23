node {
   def mvnHome
   stage('Cloning Repo') { 
      git 'https://github.com/Gauri160/JenkinsSir.git'
         
      mvnHome = tool 'MVN'
   }
   stage('Build') {
        sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean install"
       }
   stage('Results') {
         archiveArtifacts 'in28minutes-web-servlet-jsp/target/*.war'
   }
}
