pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME'
    }

    
    
    stages {    
        
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('My SonarQube Server') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
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