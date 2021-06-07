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
            sh 'mvn sonar:sonar -Dsonar.host.url=http://3.235.84.18:9000 -Dsonar.login=d9f3b0b3b3c5d2a73590012bc0503ac3b60897b1'
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
