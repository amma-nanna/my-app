  node{
   stage('SCM Checkout'){
     git 'https://github.com/javahometech/my-app'
   }
   stage('Compile-Package'){
     sh "/opt/mavan/apache-maven-3.6.0/bin/mvn package"
   }
   stage('deploy to tomcat'){
     sshagent(['tomcat']) {
     sh 'cp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/tomcat/target/*.war /opt/tomcat/apache-tomcat-8.5.39/webapps'
   }
   }
   }


