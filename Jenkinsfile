node {
   def mvnHome
   stage('Cloning Repo') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/Gauri160/JenkinsSir.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      mvnHome = tool 'MVN'
   }
   stage('Build') {
      // Run the maven build
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean install"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts 'in28minutes-web-servlet-jsp/target/*.war'
   }
   stage ('Deployment')
   {
      sh 'scp /root/.jenkins/workspace/Scripted_pipeline/in28minutes-web-servlet-jsp/target/*.war root@13.58.229.218:/opt/apache-tomcat-7.0.94/webapps/'
   }
}
