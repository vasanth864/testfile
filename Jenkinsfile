node{
   stage('SCM Checkout'){
     git 'https://github.com/vasanth864/testfile'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome = tool name: 'mymaven', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
   stage('Deploy to tomcat'){
    sshagent(['remotetomcat']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.95.211:/opt/apache-tomcat-9.0.20//webapps/'
    }
  }
  }

