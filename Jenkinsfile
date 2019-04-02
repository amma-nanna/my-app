  node{
   stage('SCM Checkout'){
     git 'https://github.com/javahometech/my-app'
   }
   stage('Compile-Package'){
     sh "/opt/mavan/apache-maven-3.6.0/bin/mvn package"
   }
   stage('deploy to tomcat'){
     sshagent(['tomcat']) {
     sh 'scp -o StrictHostKeyChecking=no /tmp/*war /opt/tomcat/apache-tomcat-8.5.39/webapps'
   }
   }
   }


