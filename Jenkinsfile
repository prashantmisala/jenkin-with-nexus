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
            sh 'mvn sonar:sonar -Dsonar.host.url=http://3.235.124.14:9000 -Dsonar.login=b18f64dbc4f49d00b4eb9a9ea9aa08f62cb066d5'
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
