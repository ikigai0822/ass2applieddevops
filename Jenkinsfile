pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME' // Name of the Maven installation
        sonarqube 'Sonar qube config'
    }

    stages {
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('SonarQube analysis') {
    withSonarQubeEnv(credentialsId: 'squ_70c05ecf9276c5c3c43ec5682ce21dd348eca187', installationName: 'My SonarQube Server') { // You can override the credential to be used
      sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
    } }

        stage('Unit test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                 sh 'mvn tomcat7:deploy'
            }
        }
    }
}