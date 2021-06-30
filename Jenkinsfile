pipeline {
    agent any 
    stages {
        stage('compile') { 
            steps {
            echo 'compile'
            sh 'mvn compile'
            }
        }
        stage('package') { 
            steps {
            echo 'package'
            sh 'mvn package'
            }
        }   
        stage('scaning'){
            steps{
            sh 'mvn sonar:sonar -Dsonar.host.url=http://34.201.151.122:9000 -Dsonar.login=5e240e942d3fb3a081399b47b8e27f11a8f5aae5'
             }
        }
        stage('nexus') { 
            steps {
            echo 'uploading'
            sh 'mvn deploy'
            }
        }
    }
}
