pipeline {
    agent any

  tools {
    maven 'MAVEN_HOME' 
  }
    stages {    
           stage ('Compile') {
          steps {
            powershell 'mvn compile'
          }
        }
        stage('SonarQube analysis') {
            steps {
            powershell 'mvn -X sonar:sonar '
          }
        }
        stage('Unit test') {
            steps {
                powershell 'mvn test'
            }
        }

        stage('Package') {
            steps {
                powershell 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                 powershell 'mvn tomcat7:run'
            }
        }
    }
}