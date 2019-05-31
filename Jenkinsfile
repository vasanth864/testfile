node{
   stage('SCM Checkout'){
     git 'https://github.com/vasanth864/testfile'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome = tool name: 'mymaven', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
}
