pipeline {
    agent any

  tools {
    maven 'MAVEN_HOME' 
  }
    stages {    
           stage ('Build') {
          steps {
            powershell 'mvn compile'
          }
        }
        stage('SonarQube analysis') {
            steps {
            powershell 'mvn -X sonar:sonar '
          }
        }
        // stage('Unit test') {
        //     steps {
        //         sh 'mvn test'
        //     }
        // }

        // stage('Package') {
        //     steps {
        //         sh 'mvn package'
        //     }
        // }

        // stage('Deploy') {
        //     steps {
        //          sh 'mvn tomcat7:deploy'
        //     }
        // }
    }
}