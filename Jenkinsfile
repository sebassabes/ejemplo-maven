pipeline {
    agent any

    stages {
        stage('compile') {
            steps {
               
                sh './mvnw.cmd clean compile -e'
                
                
            }
        }
        stage('test code') {
            steps {
               
                sh './mvnw.cmd clean test -e'
                
            }
        }
        stage('jar code') {
            steps {
              
                sh './mvnw.cmd clean package -e'
               
            }
        }
        stage('run jar') {
            steps {
                
                 sh 'JENKINS_NODE_COOKIE=dontKillMe nohup bash mvnw spring-boot:run &'
               
                
            }
        }
        stage('SonarQube analysis') {
         withSonarQubeEnv(installationName: 'sonar-scanner') { // You can override the credential to be used
          sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
    }
  }
        
    }
}
