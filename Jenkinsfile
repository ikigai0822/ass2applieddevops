pipeline {
  agent any
  tools {
    maven 'MAVEN_HOME' 
  }
    stages {    
           stage ('Build') {
          steps {
            sh 'mvn clean package'
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