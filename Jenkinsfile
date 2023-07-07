pipeline {
  agent any
  
  tools{
        jdk 'java11'
        maven 'mvn3'
        }
  
  stages {
    stage('Git Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/kelvinduan2020/Petclinic.git'
      }
    }
    
    stage('Maven Build') {
      steps {
        sh 'mvn clean install -DskipTests=true'
      }
    }
    
    stage('Deploy to Tomcat') {
      steps {
        sh 'sudo cp target/petclinic.war /opt/tomcat/apache-tomcat-9.0.65/webapps/'
      }
    }
  }
}
