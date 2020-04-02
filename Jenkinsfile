node {
      stage('SCM Checkout') {
          echo 'Git Checkout'
         git credentialsId: 'gitrepo', url: 'https://github.com/IswaryaRajendran/SpringMavenHelloWorld'
      }
      stage('Maven Build') {
            echo 'Maven Build'
            def mvnHome = tool name: 'LOCAL_MAVEN_3.6.3', type: 'maven'
            echo 'mavennnnnnnnnnnnnnnnnn'
            sh "\"${mvnHome}\"/bin/mvn package"
      }
      stage('SonarQube Analysis') {
            echo 'Sonar Buid'
            def mvnHome = tool name: 'LOCAL_MAVEN_3.6.3', type: 'maven'
            withSonarQubeEnv('Sonar_1')
            {
                  sh "\"${mvnHome}\"/bin/mvn sonar:sonar"
            }
          
      }

      stage('Deploy Tomcat') {
            sh "cp -v 'C:/Program Files (x86)/Jenkins/workspace/jenkinsfile-git-maven/target/HelloWorld.war' 'C:/Program Files/Apache Software Foundation/Tomcat 8.5/webapps'"
            echo 'Deploy Tomcat'
      }
   }
