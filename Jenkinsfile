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

      }
   }
