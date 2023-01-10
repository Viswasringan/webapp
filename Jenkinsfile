pipeline {
  agent any 
  tools {
    maven 'maven'
  }
  stages {
    stage ('Initialize') {
      steps {
        sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
            ''' 
      }
    }
    
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy-To-Tomcat') {
      steps {
        sh 'cp /var/lib/jenkins/workspace/webapp-cicd-pipeline/target/WebApp.war /home/ubuntu/prod/apache-tomcat-11.0.0-M1/webapps'
      }
    }
  }
}
