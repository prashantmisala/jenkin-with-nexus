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
        stage('tomcat'){
            steps {
            sshagent(['centos']) {
            sh 'scp -o StrictHostKeyChecking=no -r  /var/lib/jenkins/workspace/nuxes/target/WebAppCal-0.0.1.war centos@3.235.84.18:/home/centos/apache-tomcat-7.0.94/webapps/'
            }
        }
    } 
  }        
}
