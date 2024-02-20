pipeline {
  environment {
    PATH = "C:\\Program Files\\Git\\usr\\bin;C:\\Program Files\\Git\\bin;${env.PATH}"
  tools {
    maven 'MAVEN_HOME' 
  }
    stages {    
           stage ('Build') {
          steps {
            powershell 'mvn clean package'
          }
        }
        // stage('SonarQube analysis') {
        //     steps {
        //         withSonarQubeEnv('My SonarQube Server') {
        //             sh 'mvn sonar:sonar'
        //         }
        //     }
        // }
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