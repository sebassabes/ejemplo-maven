pipeline {
    agent any

    stages {
        stage('compile') {
            steps {
               
                bat './mvnw.cmd clean compile -e'
                
                
            }
        }
        stage('test code') {
            steps {
               
                bat './mvnw.cmd clean test -e'
                
            }
        }
        stage('jar code') {
            steps {
              
                bat './mvnw.cmd clean package -e'
               
            }
        }
        stage('run jar') {
            steps {
                
                 bat 'JENKINS_NODE_COOKIE=dontKillMe nohup bash mvnw spring-boot:run &'
               
                
            }
        }
     
        
    }
}
