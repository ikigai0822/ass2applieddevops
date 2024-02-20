pipeline {
    agent any

    tools {
        maven 'Maven' // Name of the Maven installation
        sonarqube 'SonarQube'
    }

    stages {
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('Code Review') {
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