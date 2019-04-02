  node{
   stage('SCM Checkout'){
     git 'https://github.com/javahometech/my-app'
   }
   stage('Compile-Package'){
    
      def mvnHome =  tool name: 'apache-maven-3.6.0', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
    stage('deploy to tomcat'){
    sshagent(['tomcat']) {
    sh 'scp -o StrictHostKeyChecking=no /tmp/*war /opt/tomcat/apache-tomcat-8.5.39/webapps'
   }
   }
   }


