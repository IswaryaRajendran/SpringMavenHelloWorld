node {
      stage('SCM Checkout') {
          echo 'Git Checkout'
         git credentialsId: 'gitrepo', url: 'https://github.com/IswaryaRajendran/SpringMavenHelloWorld'
      }
      stage('Maven Build') {
            echo 'Maven Build'
            def mvnHome = tool name: 'LOCAL_MAVEN_3.6.3', type: 'maven'
            echo 'mavennnnnnnnnnnnnnnnnn'
          sh 'mvn -Dmaven.test.failure.ignore=true install' 
      }stage('Deploy Tomcat') {
            cp -v 'C:/Program Files (x86)/Jenkins/workspace/jenkinsfile-git-maven/target/HelloWorld.war' 'C:/Program Files/Apache Software Foundation/Tomcat 8.5/webapps'
            echo 'Deploy Tomcat'
      }
   }
