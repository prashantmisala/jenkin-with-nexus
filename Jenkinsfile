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
        stage('nexus') { 
            steps {
            echo 'uploading'
            sh 'mvn deploy'
            }
        }
    }   
}
